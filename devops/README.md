# 相关概念

## 什么是DevOps

DevOps 是一套实践、工具和文化理念，可以实现软件开发团队和 IT 团队之间的流程自动化和集成。它强调团队赋能、跨团队沟通和协作以及技术自动化。

## 什么是SCM

Configuration Management，简称CM。配置管理过程是对处于不断演化、完善过程中的软件产品的管理过程。一致性、可追溯性，使产品极大程度地与用户需求相吻合。它通过控制、记录、追踪对软件的修改和每个修改生成的软件组成部件来实现对软件产品的管理功能。

> Configuration management (CM) is a systems engineering process for establishing and maintaining consistency of a product's performance, functional, and physical attributes with its requirements, design, and operational information throughout its life.[1][2] The CM process is widely used by military engineering organizations to manage changes throughout the system lifecycle of complex systems, such as weapon systems, military vehicles, and information systems. Outside the military, the CM process is also used with IT service management as defined by ITIL, and with other domain models in the civil engineering and other industrial engineering segments such as roads, bridges, canals, dams, and buildings.[3][4][5]

Software Configuration Management，简称SCM。SCM是软件工程中如何跟踪和管理软件变化的技术。

> In software engineering, software configuration management (SCM or S/W CM) is the task of tracking and controlling changes in the software, part of the larger cross-disciplinary field of configuration management. SCM practices include revision control and the establishment of baselines. If something goes wrong, SCM can determine what was changed and who changed it. If a configuration is working well, SCM can determine how to replicate it across many hosts.

随着系统越来越复杂，除了要保证交付质量，通常还面临需求变化、开发时间不充足、人员素质技能有差别等挑战，所有的挑战决定了需要采用系统化的方法来保证整个工程开发过程的顺利进行。这就是CM和SCM诞生的原因。

SCM的目的包括：

* Configuration identification - Identifying configurations, configuration items and baselines.
* Configuration control - Implementing a controlled change process. This is usually achieved by setting up a change control board whose primary function is to approve or reject all change requests that are sent against any baseline.
* Configuration status accounting - Recording and reporting all the necessary information on the status of the development process.
* Configuration auditing - Ensuring that configurations contain all their intended parts and are sound with respect to their specifying documents, including requirements, architectural specifications and user manuals.
* Build management - Managing the process and tools used for builds.
* Process management - Ensuring adherence to the organization's development process.
* Environment management - Managing the software and hardware that host the system.
* Teamwork - Facilitate team interactions related to the process.
* Defect tracking - Making sure every defect has traceability back to the source.

## 什么是 Infrastructure as Code


# 参考

- DevOps
  - [关于 DevOps 你必须知道的 11 件事](http://www.infoq.com/cn/articles/11devops)
  - [DevOps：打破开发运维的屏障](https://www.atlassian.com/zh/devops)
- SCM
  - [Wikipedia - Configuration Management](https://en.wikipedia.org/wiki/Configuration_management)
  - [Wikipedia - Software configuration management](https://en.wikipedia.org/wiki/Software_configuration_management)
  - [Comparison of open-source configuration management software](https://en.wiki2.org/wiki/Comparison_of_open-source_configuration_management_software)
- Infrastructure As Code
  - [RedHat - What is Infrastructure as Code (IaC)?](https://www.redhat.com/en/topics/automation/what-is-infrastructure-as-code-iac)
