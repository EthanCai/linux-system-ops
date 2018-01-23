<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [常用系统变量](#常用系统变量)
- [Builtin commands that are symbols](#builtin-commands-that-are-symbols)
- [Control Structures](#control-structures)
	- [if...else pattern](#ifelse-pattern)
	- [if...then...else pattern](#ifthenelse-pattern)
	- [if...then...elif pattern](#ifthenelif-pattern)
	- [for...in pattern](#forin-pattern)
	- [for pattern](#for-pattern)
	- [while pattern](#while-pattern)
	- [until pattern](#until-pattern)
	- [break and continue pattern](#break-and-continue-pattern)
	- [case pattern](#case-pattern)
	- [select pattern](#select-pattern)
- [File Descriptors](#file-descriptors)

<!-- /TOC -->


# 常用系统变量

- `$0`: 当前shell程序的名字
- `$1`~`$9`: 命令行上的第一到第九个参数
- `$#`: 命令行上的参数个数
- `$*`: 命令行上的所有参数
- `$@`: 分别用双引号引用命令行上的所有参数
- `$$`: 当前进程的进程标识号(PID)
- `$?`: 上一条命令的退出状态
- `$!`: 最后一个后台进程的进程标识号

# Builtin commands that are symbols

- `()`: subshell
- `$()`: command substitution
- `(())`: arithmetic evaluation
- `$(())`: arithmetic expansion
- `[]`: test command
- `[[]]`: conditional expression, as the modern variant of the classic test command


# Control Structures

## if...else pattern

pattern:

```bash
if test-command
    then
        commands
fi
```

example:

```bash
echo check arguments amounts
if [ $# -eq 0 ]
    then
        echo "You must supply at least one argument."
        exit 1
fi
echo "Program running..."

echo check whether file is an ordinary file
if [ -f "$1" ]
    then
        echo "$1 is an ordinary file in the working directory"
    else
        echo "$1 is NOT an ordinary file in the working directory"
fi
```

## if...then...else pattern

pattern:

```bash
if test-command
   then
       commands
   else
       commands
fi
```

example:

```bash
if [ $# -eq 0 ]
    then
        echo "Usage: out [-v] filenames..." 1>&2
        exit 1
fi

if [ "$1" = "-v" ]
    then
        shift
        less -- "$@"
    else
        cat -- "$@"
fi
```

## if...then...elif pattern

pattern:

```bash
if test-command
   then
       commands
   elif test-command
   then
       commands
   ...
   else
       commands
fi
```

example:

```bash
echo -n "word 1: "
read word1
echo -n "word 2: "
read word2
echo -n "word 3: "
read word3
if [ "$word1" = "$word2" -a "$word2" = "$word3" ]
    then
        echo "Match: words 1, 2, & 3"
    elif [ "$word1" = "$word2" ]
    then
        echo "Match: words 1 & 2"
    elif [ "$word1" = "$word3" ]
    then
        echo "Match: words 1 & 3"
    elif [ "$word2" = "$word3" ]
    then
        echo "Match: words 2 & 3"
    else
        echo "No Match"
fi
```

## for...in pattern

pattern:

```bash
for loop-index in argument-list
do
    commands
done
```

example:

```bash
for fruit in apples oranges pears bananas
do
    echo "$fruit"
done
echo "Task complete."
```

```bash
for i in *
do
    if [ -d "$i" ]
        then
            echo "$i"
    fi
done
```

## for pattern

the loop-index takes on the value of each of the command- line arguments, one at a time.

pattern:

```bash
for loop-index
do
    commands
done
```

example:

```bash
if [ $# -eq 0 ]
    then
        echo "Usage: whos id..." 1>&2
        exit 1
fi

for id
do
    mawk -F: '{print $1, $5}' /etc/passwd |
    grep -i "$id"
done
```

## while pattern

pattern:

```bash
while test-command
do
    commands
done
```

example:

```bash
number=0
while [ "$number" -lt 10 ]
do
    echo -n "$number"
    ((number +=1))
done
```

## until pattern

pattern:

```bash
until test-command
do
    commands
done
```

example:

```bash
secretname=zach
name=noname
echo "Try to guess the secret name!"
echo
until [ "$name" = "$secretname" ]
do
    echo -n "Your guess: "
    read name
done
echo "Very good."
```

## break and continue pattern

example:

```bash
for index in 1 2 3 4 5 6 7 8 9 10
do
    if [ $index -le 3 ] ; then
        echo "continue"
        continue
    fi

    echo $index

    if [ $index -ge 8 ] ; then
        echo "break"
        break
    fi
done
```

## case pattern

pattern:

```bash
case test-string in
    pattern-1)
        commands-1
        ;;
    pattern-2)
        commands-2
        ;;
    pattern-3)
        commands-3
        ;;
esac
```

example:

```bash
echo -n "Enter A, B, or C: "
read letter
case "$letter" in
    A)
        echo "You entered A"
        ;;
    B)
        echo "You entered B"
        ;;
    C)
        echo "You entered C"
        ;;
    *)
        echo "You did not enter A, B, or C"
        ;;
esac
```

## select pattern

pattern:

```bash
select varname [in arg...]
do
    commands
done
```

example:

```bash
PS3="Choose your favorite fruit from these possibilities: "
select FRUIT in apple banana blueberry kiwi orange watermelon STOP
do
    if [ "$FRUIT" == "" ]; then
        echo -e "Invalid entry.\n"
        continue
    elif [ $FRUIT = STOP ]; then
        echo "Thanks for playing!"
        break
    fi

    echo "You chose $FRUIT as your favorite."
    echo -e "That is choice number $REPLY.\n"
done
```

# File Descriptors

参考：

- [I/O Redirection](http://www.tldp.org/LDP/abs/html/io-redirection.html)
- [Bash: file descriptors](http://stackoverflow.com/questions/15606296/bash-file-descriptors)

```bash
usage ()
{
    if [ $# -ne 2 ]; then
        echo "Usage: $0 file1 file2" 2>&1
        exit 1
    fi
}

echo # Default temporary directory
: ${TEMPDIR:=/tmpdescrip}

echo #Check argument count'
usage "$@"

echo # Set up temporary files for sorting
file1=$TEMPDIR/$$.file1
file2=$TEMPDIR/$$.file2

echo # Sort
sort $1 > $file1
sort $2 > $file2

echo # Open $file1 and $file2 for reading. Use file descriptors 3 and 4.
exec 3<$file1
exec 4<$file2

echo #Read the first line from each file to figure out how to start.
read Line1 <&3
status1=$?
read Line2 <&4
status2=$?

echo #Strategy: while there is still input left in both files:
echo #Output the line that should come first.
echo #Read a new line from the file that line came from.
while [ $status1 -eq 0 -a $status2 -eq 0 ]
do
    if [[ "$Line2" > "$Line1" ]]; then
            echo -e "1.\t$Line1"
            read -u3 Line1
            status1=$?
        else
            echo -e "2.\t$Line2"
            read -u4 Line2
            status2=$?
    fi
done

echo #Now one of the files is at end-of-file.
echo #Read from each file until the end.
echo #First file1:'
while [ $status1 -eq 0 ]
do
    echo -e "1.\t$Line1"
    read Line1 <&3
    status1=$?
done

echo #Next file2:
while [[ $status2 -eq 0 ]]
do
    echo -e "2.\t$Line2"
    read Line2 <&4
    status2=$?
done

echo #Close and remove both input files
exec 3<&- 4<&-
rm -f $file1 $file2
exit 0
```

# 工具

- [Explain Shell](http://explainshell.com/)
- [ShellCheck](https://www.shellcheck.net/)


# 项目列表

- [Awesome Shell](https://github.com/alebcay/awesome-shell)
- [shunit2](https://github.com/kward/shunit2)
- [shflags](https://github.com/kward/shflags)
- [log4sh](https://github.com/kward/log4sh)
- [bats](https://github.com/sstephenson/bats)


# 参考

- [Gnu Bash Reference](http://www.gnu.org/software/bash/manual/bashref.html)
- [Linux Tools Quick Tutorial](http://linuxtools-rst.readthedocs.org/zh_CN/latest/index.html)
- [The-art-of-command-line](https://github.com/jlevy/the-art-of-command-line)
- [The Bash Hackers Wiki](http://wiki.bash-hackers.org/start)
- [Linux Shell Scripting Tutorial (LSST) v2.0](https://bash.cyberciti.biz/guide/Main_Page)
- [Shell & Utilities: Detailed Toc](http://pubs.opengroup.org/onlinepubs/9699919799/utilities/contents.html)
- [Bash-Snippets](https://github.com/alexanderepstein/Bash-Snippets)
- [每天一个linux命令目录](http://www.cnblogs.com/peida/archive/2012/12/05/2803591.html)
- IBM DeveloperWorks - Linux tmpdescrip
	- [Bash parameters and parameter expansions](https://www.ibm.com/developerworks/linux/library/l-bash-parameters/index.html)
	- [Bash test and comparison functions](https://www.ibm.com/developerworks/linux/library/l-bash-test/index.html?ca=drs-)
	- [Controlling the duration of scheduled jobs](https://www.ibm.com/developerworks/linux/library/l-job-terminating/index.html?ca=drs-)
	- [Creating a pixel ruler from the command line](https://www.ibm.com/developerworks/linux/library/l-pixelruler/index.html?ca=drs-)
	- [Finding rootfs during boot](https://www.ibm.com/developerworks/linux/library/l-boot-rootfs/index.html?ca=drs-)
	- [Job scheduling with cron and at](https://www.ibm.com/developerworks/linux/library/l-job-scheduling/index.html?ca=drs-)
