<!-- TOC START min:1 max:2 link:true update:true -->
- [1. 常用系统变量](#1-常用系统变量)
- [2. Builtin commands that are symbols](#2-builtin-commands-that-are-symbols)
- [3. Control Structures](#3-control-structures)
  - [3.1. if...else pattern](#31-ifelse-pattern)
  - [3.2. if...then...else pattern](#32-ifthenelse-pattern)
  - [3.3. if...then...elif pattern](#33-ifthenelif-pattern)
  - [3.4. for...in pattern](#34-forin-pattern)
  - [3.5. for pattern](#35-for-pattern)
  - [3.6. while pattern](#36-while-pattern)
  - [3.7. until pattern](#37-until-pattern)
  - [3.8. break and continue pattern](#38-break-and-continue-pattern)
  - [3.9. case pattern](#39-case-pattern)
  - [3.10. select pattern](#310-select-pattern)
- [4. File Descriptors](#4-file-descriptors)
- [5. 参考](#5-参考)

<!-- TOC END -->


# 1. 常用系统变量

- `$0`: 当前shell程序的名字
- `$1`~`$9`: 命令行上的第一到第九个参数
- `$#`: 命令行上的参数个数
- `$*`: 命令行上的所有参数
- `$@`: 分别用双引号引用命令行上的所有参数
- `$$`: 当前进程的进程标识号(PID)
- `$?`: 上一条命令的退出状态
- `$!`: 最后一个后台进程的进程标识号

# 2. Builtin commands that are symbols

- `()`: subshell
- `$()`: command substitution
- `(())`: arithmetic evaluation
- `$(())`: arithmetic expansion
- `[]`: test command
- `[[]]`: conditional expression, as the modern variant of the classic test command


# 3. Control Structures

## 3.1. if...else pattern

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

## 3.2. if...then...else pattern

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

## 3.3. if...then...elif pattern

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

## 3.4. for...in pattern

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

## 3.5. for pattern

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

## 3.6. while pattern

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

## 3.7. until pattern

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

## 3.8. break and continue pattern

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

## 3.9. case pattern

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

## 3.10. select pattern

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

# 4. File Descriptors

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


# 5. 参考

- Shell Tutorial
  - [Gnu Bash Reference](http://www.gnu.org/software/bash/manual/bashref.html)
  - [The-art-of-command-line](https://github.com/jlevy/the-art-of-command-line)
  - [The Bash Hackers Wiki](http://wiki.bash-hackers.org/start)
  - [Linux Shell Scripting Tutorial (LSST) v2.0](https://bash.cyberciti.biz/guide/Main_Page)
  - [Pure Bash Bible](https://github.com/dylanaraps/pure-bash-bible):  A collection of pure bash alternatives to external processes
  - [Shell & Utilities: Detailed Toc](http://pubs.opengroup.org/onlinepubs/9699919799/utilities/contents.html)
  - [Advanced Bash-Scripting Guide](https://linux.die.net/abs-guide/index.html)
html)
- Collection of bash scripts
  - [Bash-Oneliner](https://github.com/onceupon/Bash-Oneliner)
  - [Bash-Snippets](https://github.com/alexanderepstein/Bash-Snippets)
- Tools
  - [Explain Shell](http://explainshell.com/)
  - [ShellCheck](https://www.shellcheck.net/)
- Libraries
  - [shunit2](https://github.com/kward/shunit2)
  - [shflags](https://github.com/kward/shflags)
  - [log4sh](https://github.com/kward/log4sh)
  - [bats](https://github.com/sstephenson/bats)
- IBM DeveloperWorks
  - [Bash parameters and parameter expansions](https://developer.ibm.com/tutorials/l-bash-parameters/)
  - [Bash test and comparison functions](https://developer.ibm.com/tutorials/l-bash-test/)
  - [Controlling the duration of scheduled jobs](https://www.ibm.com/developerworks/linux/library/l-job-terminating/)
  - [Creating a pixel ruler from the command line](https://www.ibm.com/developerworks/library/l-pixelruler/index.html)
  - [Finding rootfs during boot](https://developer.ibm.com/tutorials/l-boot-rootfs/)
  - [Job scheduling with cron and at](https://www.ibm.com/developerworks/library/l-job-scheduling/index)
- Other
  - [Awesome Shell](https://github.com/alebcay/awesome-shell)
