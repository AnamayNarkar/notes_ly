# DevOps - Module 1: DevOps Fundamentals and Linux Environment

> **Source material:** 1.1 DevOps Basic.pdf, 1.2 Linux.pdf, Devops Intro and Jenkins.pptx  
> **PYQs used:** DevOps.PDF (ESE Jul-Nov 2025), ESE DevOPs_QP_SVU2020, ISE_DEVOPS, Re-ISE, Sample.pdf  
> Items marked **[CONSTRUCTED]** are not explicitly in the provided notes/PYQs but are part of the syllabus and are expected exam topics.

---

## 1. Topic Map

```
Module 1: DevOps Fundamentals and Linux Environment
|
+-- 1.1 Introduction to DevOps and SDLC
|   |
|   +-- What is DevOps
|   |   +-- Definition and origin (Patrick Debois, 2009)
|   |   +-- Development + Operations
|   |   +-- DevOps Trinity: People, Process, Technology
|   |
|   +-- SDLC Models (before DevOps)
|   |   +-- Waterfall Model
|   |   |   +-- Phases: Requirements -> Design -> Implementation -> Verification -> Maintenance
|   |   |   +-- Drawbacks
|   |   +-- Agile Model
|   |       +-- Iterative approach (sprints 1-3 weeks)
|   |       +-- Drawback: Dev works, Ops doesn't
|   |
|   +-- Why DevOps (Need for DevOps)
|   |
|   +-- DevOps Lifecycle (7 Phases / Infinity Loop)
|   |   +-- Plan
|   |   +-- Code
|   |   +-- Build
|   |   +-- Test
|   |   +-- Integrate
|   |   +-- Deploy
|   |   +-- Operate
|   |   +-- Monitor
|   |
|   +-- 7 Cs of DevOps
|   |   +-- Continuous Development
|   |   +-- Continuous Integration (CI)
|   |   +-- Continuous Testing
|   |   +-- Continuous Deployment (CD)
|   |   +-- Continuous Feedback
|   |   +-- Continuous Monitoring
|   |   +-- (Continuous Collaboration - implied)
|   |
|   +-- Benefits of DevOps
|   +-- DevOps Tools (per phase)
|   +-- DevOps Culture
|       +-- Affinity
|       +-- Trust and Empathy
|       +-- Folk Model
|       +-- Old View vs New View
|
+-- Introduction to Operating Systems  [CONSTRUCTED]
|   +-- What is an OS
|   +-- Types of OS
|   +-- OS Functions
|
+-- Virtualization and Virtual Machines
|   +-- What is Virtualization
|   +-- Hypervisor (Type 1 and Type 2)
|   +-- VMware and VirtualBox
|   +-- Physical Machine vs Virtual Machine
|   +-- Advantages and Limitations
|
+-- Linux File System and CLI
|   +-- Why Linux in DevOps
|   +-- Shell Types (sh, csh, zsh, bash)
|   +-- Linux FHS (Filesystem Hierarchy Standard)
|   |   +-- / (root), /bin, /etc, /home, /var, /usr, /opt, /tmp, /root, /proc, /dev
|   +-- Basic Navigation Commands
|       +-- echo, ls, cd, pwd, mkdir, cp, mv, rm, cat, touch
|       +-- Wildcards (* and ?)
|       +-- Absolute vs Relative Paths
|
+-- 1.2 Basic Linux Commands, Pipes and Redirects
|   +-- Standard Streams: stdin, stdout, stderr
|   +-- Redirection: >, >>, <, 2>, 2>&1, &>
|   +-- Pipes: | (chaining commands)
|   +-- Useful filter commands: grep, wc, sort, awk, uniq, tee
|
+-- Linux Package Managers
|   +-- RPM-based: rpm, yum, dnf
|   |   +-- YUM repos (/etc/yum.repos.d)
|   +-- Debian-based: apt, dpkg
|
+-- Vim Editor
|   +-- Modes: Normal, Insert, Command
|   +-- Essential commands
|
+-- Users, Groups, Permissions and Ownership
|   +-- Users: useradd, usermod, userdel, passwd
|   +-- Groups: groupadd, groupmod, groupdel
|   +-- Ownership: chown, chgrp
|   +-- Permissions: chmod (symbolic and octal)
|   +-- sudo and /etc/sudoers
|   +-- id, whoami, su
|
+-- Environment Variables and SSH
    +-- Environment Variables
    |   +-- What they are
    |   +-- export, echo $VAR, env, printenv
    |   +-- Persistent vars in ~/.bashrc or /etc/environment
    +-- SSH (Secure Shell)
        +-- ssh command syntax
        +-- Key-based authentication (ssh-keygen, ssh-copy-id)
        +-- /etc/ssh/sshd_config
```

---

## 2. Topic-wise Question Types

Legend: **[PYQ]** = has appeared in an actual past question paper

| Topic | Theory / Explain | Definition / Short Note | List / Enumerate | Diagram | Compare / Differentiate | Scenario / Application | Command Writing |
|---|---|---|---|---|---|---|---|
| What is DevOps | **[PYQ]** | **[PYQ]** | - | - | - | - | - |
| Need for DevOps | **[PYQ]** | - | **[PYQ]** | - | - | **[PYQ]** | - |
| Waterfall Model | **[PYQ]** | - | drawbacks | **[PYQ]** | **[PYQ]** | - | - |
| Agile Model | **[PYQ]** | - | - | **[PYQ]** | **[PYQ]** | - | - |
| DevOps Lifecycle (phases) | **[PYQ]** | - | - | **[PYQ]** | - | **[PYQ]** | - |
| 7 Cs of DevOps | **[PYQ]** | **[PYQ]** | **[PYQ]** | **[PYQ]** | - | - | - |
| Benefits of DevOps | - | - | **[PYQ]** | - | - | - | - |
| DevOps Tools | - | - | **[PYQ]** | **[PYQ]** | - | - | - |
| DevOps Trinity (PPT) | **[PYQ]** | - | - | - | - | - | - |
| DevOps Culture / Affinity | **[PYQ]** | **[PYQ]** | - | - | - | **[PYQ]** | - |
| Trust and Empathy in DevOps | **[PYQ]** | - | - | - | - | **[PYQ]** | - |
| DevOps Folk Model | **[PYQ]** | **[PYQ]** | - | - | - | - | - |
| Old View vs New View | **[PYQ]** | - | - | - | **[PYQ]** | - | - |
| Goals of Dev/Release/Deploy | **[PYQ]** | - | - | - | - | - | - |
| Operating Systems (intro) | Theory | Short Note | - | - | - | - | - |
| Virtualization and VMs | **[PYQ]** | - | adv/dis | - | **[PYQ]** | **[PYQ]** | - |
| Linux File System (FHS) | **[PYQ]** | - | - | **[PYQ]** | - | **[PYQ]** | **[PYQ]** |
| Shell Types | Short Note | - | - | - | - | - | - |
| Basic Linux Commands | - | - | - | - | - | **[PYQ]** | **[PYQ]** |
| Pipes and Redirection | **[PYQ]** | - | - | - | **[PYQ]** | **[PYQ]** | **[PYQ]** |
| Package Managers (RPM/YUM/APT) | **[PYQ]** | - | - | - | **[PYQ]** | - | **[PYQ]** |
| Vim Editor | - | Short Note | - | - | - | - | **[PYQ]** |
| Users, Groups, Permissions | **[PYQ]** | - | - | - | - | **[PYQ]** | **[PYQ]** |
| chmod / chown / chgrp | **[PYQ]** | - | - | - | - | **[PYQ]** | **[PYQ]** |
| sudo / sudoers | Theory | - | - | - | - | - | - |
| Environment Variables | **[PYQ]** | - | - | - | - | **[PYQ]** | **[PYQ]** |
| SSH | **[PYQ]** | - | - | - | - | **[PYQ]** | **[PYQ]** |

---

## 3. Topic-by-Topic Detailed Breakdown

---

### 3.1 What is DevOps

**The Simple Explanation:**

DevOps = Development + Operations. It is not just a tool or a process - it is a **culture** and a set of practices that brings the development team and the IT operations team together to deliver software faster and more reliably.

The term was coined by **Patrick Debois in 2009**. Before DevOps, developers would write code and "throw it over the wall" to operations, who would then deploy it. This caused friction - "it works on my machine but not on the server."

**Formal Definition:**

DevOps is the combination of cultural philosophies, practices, and tools that increases an organization's ability to deliver applications and services at high velocity - evolving and improving products at a faster pace than organizations using traditional methods.

**The DevOps Trinity (3 pillars):**

1. **People and Culture** - Break down silos between Dev and Ops. Shared ownership, shared goals.
2. **Processes and Practices** - Adopt Agile, Scrum, Kanban + automation to streamline work in predictable, repeatable ways.
3. **Tools and Technologies** - Enable automation, CI, configuration management, testing, packaging, releasing, and monitoring. Without tools, DevOps is not sustainable.

**How to answer in exam (short note style):**

DevOps is a cultural and professional movement that emphasizes communication, collaboration, integration, and automation between development and operations teams. It defines practices for designing, developing, testing, deploying, managing environments, gathering feedback, and doing continuous improvements. The core idea: Dev and Ops work together throughout the entire software lifecycle.

---

### 3.2 SDLC Models - Waterfall and Agile (context for DevOps)

**Why this matters:** The exam frequently asks "why DevOps over Waterfall/Agile" so you need to know both models and their drawbacks.

#### Waterfall Model

A **sequential** SDLC model. Each phase must complete before the next begins. Output of one phase = input of next.

**Phases (draw this as a staircase going downward):**

```
Requirements
    |
    v
  Design
    |
    v
Implementation
    |
    v
Verification
    |
    v
Maintenance
```

**Drawbacks:**
- Changes to a previous stage are very difficult
- Not suitable for large projects
- Developers and testers do not work together - bugs surface late
- Takes a very long time to deploy code
- Not suited for changing requirements
- Difficult to give feedback on product

#### Agile Model

Agile breaks the project into **multiple short iterations (1-3 weeks each)**. Each iteration delivers a working product increment. Teams work simultaneously on Requirements, Design, Development, and Release within each sprint.

**The problem with Agile alone:** The code that works for the developer may NOT work for the operations team - the "works on my machine" problem persists because Agile only addresses the Dev side.

#### DevOps over Agile and Waterfall

DevOps solves this by adding **continuous integration** between deployment and testing, plus **near real-time monitoring** and immediate feedback. Both developer and operations team work together, so code works on both sides.

**Comparison Table (exam-ready):**

| Aspect | Waterfall | Agile | DevOps |
|---|---|---|---|
| Approach | Sequential | Iterative | Continuous |
| Delivery | One final release | End of each sprint | Continuous deployment |
| Team structure | Separate Dev/Test/Ops | Dev + QA (still separate from Ops) | Dev + Ops integrated |
| Feedback | Very late | After each sprint | Real-time / continuous |
| Risk | High (late failure detection) | Medium | Low (early detection) |
| Changes | Costly | Manageable | Easy |

---

### 3.3 Need for DevOps

Six main drivers (from notes - draw these as a web/spider diagram around a central building icon):

1. **Increased rate of application releases** - Business requires speedy deployment to production
2. **Very short duration to implement** - Changes must reach the customer fast
3. **Different priorities** - Dev team (new features), QA (stability), Ops team (reliability) have conflicting goals
4. **To manage different environments** - Standardized environments so changes are accommodated easily
5. **Effective application monitoring** - Need effective process for monitoring and management
6. **Collaborative culture + automation** - To keep up with speed of change and manage risk

**Cloud computing** enabled DevOps - it opened doors for automation, scalability, and rapid provisioning of environments.

---

### 3.4 DevOps Lifecycle (The Infinity Loop)

The DevOps lifecycle is visualized as an **infinity (figure-8) loop** to show it is continuous and never-ending.

**Draw this diagram in exam:**

![](https://cdn.ttgtmedia.com/rms/onlineimages/itops-devops_infinity_loop-f.png)

The left loop = Development side (Plan, Code, Build, Test)
The right loop = Operations side (Deploy, Operate, Monitor, Integrate back)

**7 phases explained:**

| Phase | What happens | Key point |
|---|---|---|
| **Plan** | Define vision, project requirements, backlog | Future iterations are planned with past iteration data in mind |
| **Code** | Write code per specifications from planning phase | Code is written with operations in mind |
| **Build** | Introduce code to project, rebuild if necessary | GitHub / version control is used |
| **Test** | Test for bugs, edge cases, corner cases | Edge case = extreme operating event; Corner case = multiple circumstances met |
| **Integrate** | Final check for production readiness | Code verified as ready for deployment |
| **Deploy** | Release to production environment | Shared responsibility between Dev and Ops |
| **Operate** | End users use the product in production | Informs future development cycles |
| **Monitor** | Track product usage, feedback, issues | Information fed into next iteration |

---

### 3.5 The 7 Cs of DevOps

The 7 Cs map to the lifecycle phases and describe the **continuous practices** in DevOps:

| C | Phases it covers | Key tools/notes |
|---|---|---|
| **Continuous Development** | Plan + Code | Git, GitHub - product backlog maintained, released in smaller milestones |
| **Continuous Integration (CI)** | Build + Test + Integrate | Jenkins, Bamboo - most important stage; code tested before every commit; defects caught early |
| **Continuous Testing** | Test | Selenium, TestNG, JUnit - uses Docker containers for test environments |
| **Continuous Deployment (CD)** | Deploy | Puppet, Chef, Docker - involves configuration management for consistent deployments |
| **Continuous Feedback** | Operate | Surveys (structured), social media (unstructured) - client behavior examined per release |
| **Continuous Monitoring** | Monitor | Nagios, Splunk - monitors for system faults like low memory, server unreachable |
| **Continuous Collaboration** | All phases (implied) | The cultural glue that holds all Cs together |

**CI is the most important C** - it transforms integration from a one-time event to a continuous process where code is tested before every commit.

---

### 3.6 Benefits of DevOps

(Frequently asked as "list 5 benefits" - memorize 7 to be safe)

1. Continuous delivery of software
2. Better collaboration between teams
3. Easy deployment
4. Better efficiency and scalability
5. Errors are fixed at the initial stage (early detection of failures)
6. More security
7. Less manual intervention (fewer chances of error)
8. Better resource utilization
9. Faster time to market
10. Transparency in execution

---

### 3.7 DevOps Tools (per lifecycle phase)

```
Plan/Code:   Git, SVN (Subversion), IntelliJ IDEA
Build:       Maven, Gradle
Test:        Selenium, JUnit, TestNG
Integrate:   Jenkins, Bamboo
Deploy:      Puppet, Chef, Docker
Operate:     Docker, Chef
Monitor:     Nagios, Splunk
```

---

### 3.8 DevOps Culture Topics (High-priority for exam)

#### Affinity in DevOps

**Definition:** Affinity in DevOps refers to the natural alignment and closeness between Development and Operations teams - a shared sense of ownership, goals, and mutual understanding that makes them function as one team rather than two separate silos.

**Significance for high-performing teams:**
- Teams with high affinity share responsibility for both code and deployment
- Reduces blame culture ("not my problem") 
- Leads to blameless postmortems - when something fails, the team analyzes the system, not the individual
- Creates psychological safety - people share problems without fear of blame
- Results in faster issue resolution because both teams understand each other's constraints

#### Trust and Empathy in DevOps

These are **cultural prerequisites** for DevOps transformation, not technical ones.

**Trust:**
- Developers trust Ops to deploy reliably; Ops trusts Devs to write production-ready code
- Trust is built through shared ownership, transparency, and blameless culture
- Without trust, teams hide failures instead of reporting them

**Empathy:**
- Devs who understand Ops constraints write more deployable code
- Ops who understand Dev pressures set realistic deployment windows
- Practical steps: job shadowing (Dev works with Ops for a week), shared on-call rotations, joint postmortems

**How empathy and trust contribute to DevOps success:**
1. Breaks down the "wall" between Dev and Ops
2. Teams proactively share knowledge of upcoming changes
3. Reduces time wasted in finger-pointing during incidents
4. Enables the "you build it, you run it" culture

#### DevOps Folk Model

**What it is:** The "Folk Model" of DevOps is the informal, varying understanding people have of what DevOps means. Different people in an organization interpret DevOps differently:

- Manager's view: "DevOps = faster releases"
- Developer's view: "DevOps = automation scripts"
- Ops engineer's view: "DevOps = they want us to code now"
- Tool vendor's view: "DevOps = our product"

**Why it matters:** Because there is no single universal definition, organizations adopting DevOps may implement it inconsistently. Some focus only on tools (CI/CD pipelines) while ignoring culture. This leads to "DevOps theater" - going through the motions without real transformation.

**The correct understanding:** DevOps is a sociotechnical transformation - it is simultaneously about culture (people), processes, AND tools. Focusing on only one dimension fails.

**In exam:** Write about how DevOps means different things to different stakeholders, and why a unified, holistic understanding (people + process + technology) is essential for successful DevOps adoption.

#### Old View vs New View of Software Delivery

| Dimension | Old View | New View |
|---|---|---|
| Failures cause | Human error - someone is to blame | Emergent from complex systems, not individual fault |
| Response to failure | Punish the person who made the mistake | Blameless postmortem - understand the system |
| Ops view of Dev | "Developers create chaos" | Partners in delivering value |
| Dev view of Ops | "Ops blocks releases" | Partners who keep the system stable |
| Deployment frequency | Infrequent (batched, risky) | Frequent, small, low-risk |
| Testing | Done by a separate QA team at the end | Everyone's responsibility, continuous |
| Documentation | Heavy upfront docs | Living documentation, working software |
| Monitoring | Ops monitors; Dev doesn't care | Shared ownership - "you build it, you run it" |

**New View is more relevant** because modern software systems are complex - failures are rarely caused by one person. The New View promotes learning and improvement rather than blame.

#### Goals of Development, Release, and Deployment in DevOps

**Development:**
- Goal: Continuously add value through new features and bug fixes
- Code should be production-ready from day one, not just dev-environment-ready
- Uses version control, feature branches, and peer review

**Release:**
- Goal: Make a tested, versioned artifact ready for production
- Every release should be a low-stress, routine event (not a big scary occasion)
- Involves release notes, semantic versioning, artifact storage in repositories

**Deployment:**
- Goal: Get the released artifact running in production reliably, repeatably, and with minimal downtime
- Automated deployments eliminate human error
- Configuration management (Puppet, Chef, Ansible) ensures consistency across environments
- Rollback plans must exist for every deployment

---

### 3.9 Introduction to Operating Systems [CONSTRUCTED]

**What is an Operating System:**
An OS is system software that manages computer hardware and software resources and provides common services for computer programs. It is the intermediary between users/applications and the hardware.

**Key functions:**
- Process management (scheduling CPU time)
- Memory management (RAM allocation)
- File system management (organizing data on disk)
- Device management (drivers for hardware)
- Security and access control
- Network management

**Types of OS:**
- **Single-user, single-tasking:** DOS
- **Single-user, multi-tasking:** Windows, macOS
- **Multi-user:** Linux, Unix
- **Real-time OS:** Used in embedded systems, aviation, medical devices

**Why Linux for DevOps:** 53.3% of professional developers use Linux (StackOverflow 2019); 83.1% love it. Most cloud servers run Linux. Most DevOps tools are built for Linux.

---

### 3.10 Virtualization and Virtual Machines

**What is Virtualization:**

Virtualization is the technology of creating a software-based (virtual) version of computing resources including servers, storage, networks, and operating systems. A single physical machine can host multiple virtual machines simultaneously.

**How it works - The Hypervisor:**

A **hypervisor** (also called Virtual Machine Monitor / VMM) is software that creates and manages virtual machines.

**Type 1 Hypervisor (Bare-Metal):**
- Runs directly on hardware, no host OS needed
- Examples: VMware ESXi, Microsoft Hyper-V, Xen
- Used in data centers and cloud providers
- Better performance and security

**Type 2 Hypervisor (Hosted):**
- Runs on top of a host OS (Windows/macOS/Linux)
- Examples: **VMware Workstation**, **VirtualBox** (Oracle)
- Used on developer/student laptops
- Easier to set up, slightly more overhead

```
Physical Machine Architecture:

Type 1 (Bare-Metal):           Type 2 (Hosted):
+------------------+           +------------------+
| VM1 | VM2 | VM3  |           | VM1 | VM2 | VM3  |
+------------------+           +------------------+
|    Hypervisor    |           |    Hypervisor    |
+------------------+           +------------------+
|    Hardware      |           |    Host OS       |
+------------------+           +------------------+
                                |    Hardware      |
                                +------------------+
```

**Physical Machine vs Virtual Machine:**

| Aspect | Physical Machine | Virtual Machine |
|---|---|---|
| Hardware | Dedicated hardware | Shared hardware (virtualized) |
| Isolation | Full (separate machine) | Isolated at OS level |
| Cost | High (separate server per use) | Low (multiple VMs per server) |
| Setup time | Days/weeks | Minutes |
| Resource utilization | Often underutilized | Efficient sharing |
| Failure impact | Affects only that machine | Can affect all VMs on the host |
| Portability | Difficult to move | Snapshot and migrate easily |

**VMware and VirtualBox:**

- **VMware Workstation/Player:** Commercial (free version available), better performance, widely used in enterprise
- **Oracle VirtualBox:** Open source and free, excellent for students and labs, cross-platform

**Advantages of VMs for DevOps:**
- Quickly spin up test/dev environments
- Snapshot before risky changes (rollback if needed)
- Run multiple OS on one machine
- Infrastructure as code - VMs provisioned by scripts
- Cost efficient

**Limitations:**
- Each VM has its own full OS = large disk/RAM footprint
- Slower boot times compared to containers
- Hypervisor overhead affects performance
- Not as lightweight as containers (Docker) for microservices

---

### 3.11 Linux File System and CLI

**Why Linux in DevOps:** Most production servers, CI/CD pipelines, and cloud infrastructure run on Linux. A DevOps engineer who cannot navigate Linux is handicapped.

#### Shell Types

The shell is the command-line interpreter - it takes your commands and executes them.

```bash
echo $SHELL     # check current shell
# output: /bin/bash
```

| Shell | Name | Notes |
|---|---|---|
| sh | Bourne Shell | Original Unix shell, minimal |
| csh / tcsh | C Shell | C-like syntax |
| zsh | Z Shell | Modern, popular on macOS |
| bash | Bourne Again Shell | Most common on Linux, recommended |

#### Linux Filesystem Hierarchy Standard (FHS)

Draw this as a tree in exam:

```
/   (root - everything starts here)
|
+-- /bin        Essential user binaries (ls, cp, mv, cat)
+-- /sbin       System binaries (ifconfig, fsck) - for root
+-- /etc        Configuration files (passwd, sudoers, ssh/sshd_config)
+-- /home       User home directories (/home/username)
+-- /root       Home directory of root user (NOT /home/root)
+-- /var        Variable data: logs (/var/log), spool, mail
+-- /tmp        Temporary files (cleared on reboot)
+-- /usr        User programs and data
|   +-- /usr/bin    User commands (python, git)
|   +-- /usr/lib    Libraries for user programs
+-- /opt        Optional/third-party software (Jenkins, custom apps)
+-- /proc       Virtual filesystem - running processes and kernel info
+-- /dev        Device files (disks, terminals, null)
+-- /boot       Boot loader files, kernel images
+-- /lib        Essential shared libraries
+-- /mnt        Temporary mount point
+-- /media      Removable media mount points
```

**Key directories for DevOps (memorize these):**

| Directory | Purpose | DevOps Use |
|---|---|---|
| /etc | Config files | Edit app configs, sshd_config, sudoers |
| /var/log | Log files | Check app/system logs for debugging |
| /home | User files | Developer home directories |
| /opt | Optional software | Install Jenkins, custom tools |
| /tmp | Temp files | Temp artifacts during builds |
| /usr/bin | User programs | Where installed commands live |

#### Basic Navigation and File Commands

```bash
# Navigation
echo "Hello"          # Print to screen
ls                    # List files and folders
ls -la                # Detailed list including hidden files
cd /path/to/dir       # Change directory
cd ..                 # Go up one level
cd ~                  # Go to home directory
pwd                   # Print working directory (current location)

# Directory operations
mkdir new_dir                         # Create directory
mkdir -p /tmp/asia/india/bangalore    # Create nested directories in one command
cp -r source_dir /tmp/dest_dir        # Copy directory recursively
rm -r /tmp/dir                        # Remove directory recursively
mv old_dir new_dir                    # Rename/move directory

# File operations
touch new_file.txt                    # Create empty file
cat > new_file.txt                    # Write to file (Ctrl+D to end)
cat new_file.txt                      # View file contents
cp source.txt dest.txt                # Copy file
mv old.txt new.txt                    # Rename/move file
rm file.txt                           # Delete file

# Download files
curl http://example.com/file.txt -O   # Download, keep original name
wget http://example.com/file.txt      # Download file

# Check OS version
cat /etc/*release*
```

#### Paths and Wildcards

```bash
/var/log/app.log       # Absolute path - starts from /
./app.log              # Relative path - starts from current directory
.                      # Current directory
..                     # Parent directory
~                      # Home directory

ls *.log               # * matches any sequence of characters
ls file?.txt           # ? matches exactly one character
ls file[1-3].txt       # Matches file1.txt, file2.txt, file3.txt
```

---

### 3.12 Pipes and Redirection

This is one of the highest-frequency exam topics. Understand the concept deeply.

#### Standard Streams

Every Linux process has 3 standard streams:

| Stream | Number | Direction | Purpose |
|---|---|---|---|
| stdin | 0 | Input to program | Keyboard / file / another command |
| stdout | 1 | Output from program | Terminal / file / another command |
| stderr | 2 | Error output | Terminal / separate file |

#### Redirection Operators

```bash
# stdout redirection
ls -l > files.txt              # Write stdout to file (OVERWRITES existing content)
ls -l >> files.txt             # Append stdout to file

# stdin redirection
sort < names.txt               # Feed file as stdin to sort command

# stderr redirection
find / -name "*.conf" 2> errors.log     # Redirect stderr to file
find / -name "*.conf" 2>> errors.log    # Append stderr to file

# Combine stdout and stderr
command 2>&1                   # Redirect stderr to same place as stdout
command &> all-output.log      # Redirect both to file (bash shorthand)
```

#### Pipe Operator

The pipe `|` sends the **stdout of one command** to the **stdin of the next command**. It chains commands together.

```bash
# Count running python processes
ps aux | grep python

# Find 10 largest files
du -ah . | sort -h | tail -10

# Count error lines in a log
grep "ERROR" app.log | wc -l

# Extract unique usernames from process list
ps aux | awk '{print $1}' | sort | uniq

# DevOps scenario: filter errors, save to file, AND count them simultaneously
# tee reads from stdin and writes to both stdout AND a file
grep -i 'error' app.log | tee error-only.log | wc -l
```

#### Comparison Table (exam favorite)

| Operator | Name | Effect |
|---|---|---|
| `>` | Output redirect (overwrite) | Sends stdout to file, replaces existing content |
| `>>` | Output redirect (append) | Sends stdout to file, adds to existing content |
| `<` | Input redirect | Feeds file content as stdin to command |
| `|` | Pipe | Connects stdout of left command to stdin of right command |
| `2>` | Error redirect | Sends stderr to file |
| `2>&1` | Merge streams | Redirects stderr to wherever stdout is going |
| `&>` | Both redirect | Sends stdout + stderr to file |
| `tee` | T-pipe | Writes to file AND passes through to stdout |

---

### 3.13 Linux Package Managers

A package manager automatically **installs software, resolves dependencies, upgrades, and removes** packages. This is far better than manually downloading and installing binaries.

#### Two Major Families

**RPM-based (Red Hat, CentOS, Fedora):**

```bash
# rpm - low level, works with .rpm files directly (NO dependency resolution)
rpm -i telnet.rpm           # Install package
rpm -e telnet               # Uninstall package
rpm -q telnet               # Query (check if installed)
rpm -qa                     # List ALL installed RPMs
rpm -qi nginx               # Package information
rpm -ql nginx               # List files installed by package

# yum - higher level, resolves dependencies, uses repos
yum install nginx           # Install package + dependencies
yum update                  # Update all packages
yum remove nginx            # Remove package
yum repolist                # List configured repos

# dnf - modern replacement for yum (recommended)
dnf search nginx            # Search for package
dnf install nginx           # Install
dnf update                  # Update all
dnf remove nginx            # Remove
dnf list installed          # List installed packages
dnf info nginx              # Show package details
```

**YUM uses repo configuration files at `/etc/yum.repos.d/`**

**Debian-based (Ubuntu, Debian):**

```bash
# apt - high level package manager
sudo apt update             # Refresh package index (run this first!)
sudo apt upgrade            # Upgrade all installed packages
sudo apt install nginx      # Install package
sudo apt remove nginx       # Remove package
apt search nginx            # Search
apt show nginx              # Show package info

# dpkg - low level, works with .deb files directly (NO dependency resolution)
dpkg -l                     # List installed packages
dpkg -s nginx               # Package status
dpkg -L nginx               # Files installed by package
sudo dpkg -i package.deb    # Install a .deb file
sudo apt -f install         # Fix broken dependencies after dpkg install
```

**Comparison Table:**

| Aspect | RPM/YUM/DNF | APT/DPKG |
|---|---|---|
| Used on | Red Hat, CentOS, Fedora | Debian, Ubuntu, Mint |
| Package format | .rpm | .deb |
| Low-level tool | rpm | dpkg |
| High-level tool | yum / dnf | apt |
| Repo config | /etc/yum.repos.d/ | /etc/apt/sources.list |
| Dependency resolution | Yes (yum/dnf) | Yes (apt) |

---

### 3.14 Vim Editor

Vim is the standard terminal-based text editor on Linux. It is used to edit configuration files, scripts, and code on remote servers.

**Vim has MODES** (this trips people up - you must know the modes):

| Mode | How to enter | What you can do |
|---|---|---|
| Normal | Press Esc | Navigate, delete, copy, paste, search |
| Insert | Press i (before cursor) or a (after cursor) or o (new line below) | Type/edit text |
| Command | Press : (colon) from Normal mode | Save, quit, search and replace |

**Essential Commands:**

```
--- From Normal Mode ---
i          Enter Insert mode (before cursor)
a          Enter Insert mode (after cursor)
o          Open new line below and enter Insert mode
Esc        Return to Normal mode (ALWAYS press this first if stuck)

dd         Delete (cut) entire line
yy         Yank (copy) entire line
p          Paste below current line
u          Undo last action
Ctrl+r     Redo

/pattern   Search for pattern (press n for next match, N for previous)
G          Go to end of file
gg         Go to beginning of file

--- Command Mode (type : then the command) ---
:w         Save (write) file
:q         Quit (only if no unsaved changes)
:wq        Save and quit
:q!        Quit WITHOUT saving (force quit)
:set nu    Show line numbers
```

**Practical workflow:**
```bash
vim app.conf          # Open file
# Press i             # Enter insert mode
# Type your config    # Edit
# Press Esc           # Return to normal mode
# Type :wq            # Save and quit
```

---

### 3.15 Users, Groups, Permissions and Ownership

This is a critical exam topic - expect a scenario question or a "write commands" question.

#### User Management Commands

```bash
# Create a user
useradd developer1                    # Create user (no home dir by default on some systems)
useradd -m developer1                 # Create user WITH home directory
useradd -m -s /bin/bash developer1    # With home dir and bash shell

# Set password
passwd developer1                     # Set/change password for developer1

# Delete user
userdel developer1                    # Delete user (keep home dir)
userdel -r developer1                 # Delete user AND home directory

# Check current user
whoami                    # Print current username
id                        # Print UID, GID, and groups

# Switch user
su developer1             # Switch to developer1 (requires their password)
su - developer1           # Switch to developer1 with their environment

# Remote login
ssh developer1@192.168.1.2
```

#### Group Management Commands

```bash
groupadd developers                   # Create group
groupadd testers

usermod -aG developers developer1     # Add developer1 to developers group
usermod -aG developers developer2     # Add developer2 to developers group
usermod -aG testers tester1

groupdel developers                   # Delete group
groups developer1                     # Show groups of a user
```

#### Linux Permission System

Every file/directory in Linux has:
- **Owner** (user) - one user who owns it
- **Group** - one group associated with it
- **Others** - everyone else

Each of these three has three permission bits: **r (read), w (write), x (execute)**

**Reading permission output from `ls -la`:**

```
-rwxr-x---  1  alice  developers  4096  Oct 27  app.sh
```

Breaking down `-rwxr-x---`:

```
- rwx r-x ---
| ||| ||| |||
| ||| ||| +++--> Others permissions: --- (no read, no write, no execute)
| ||| |||
| ||| ++-------> Group permissions: r-x (read, no write, execute)
| |||
| +++-----------  Owner permissions: rwx (read, write, execute)
|
+-------------- File type: - = regular file, d = directory, l = symlink
```

**Octal representation (memorize for chmod):**

| Permission | Symbol | Octal |
|---|---|---|
| No permission | --- | 0 |
| Execute only | --x | 1 |
| Write only | -w- | 2 |
| Write + Execute | -wx | 3 |
| Read only | r-- | 4 |
| Read + Execute | r-x | 5 |
| Read + Write | rw- | 6 |
| Read + Write + Execute | rwx | 7 |

**Common permission combinations:**

| Octal | Symbol | Meaning |
|---|---|---|
| 777 | rwxrwxrwx | Everyone has full access (dangerous) |
| 755 | rwxr-xr-x | Owner full, group/others read+execute |
| 750 | rwxr-x--- | Owner full, group read+execute, others nothing |
| 644 | rw-r--r-- | Owner read+write, group/others read only |
| 600 | rw------- | Owner read+write only, no one else |
| 400 | r-------- | Owner read only (SSH private key permission) |

#### chmod - Change Permissions

```bash
# Octal method
chmod 755 script.sh               # rwxr-xr-x
chmod 644 config.conf             # rw-r--r--
chmod 750 app_directory/          # rwxr-x---

# Symbolic method
chmod u+x script.sh               # Add execute for user/owner
chmod g-w file.txt                # Remove write from group
chmod o=r file.txt                # Set others to read-only
chmod a+r file.txt                # Add read for ALL (user, group, others)
chmod u=rwx,g=rx,o= app.sh        # Set permissions explicitly
```

#### chown - Change Ownership

```bash
chown alice file.txt              # Change owner to alice
chown alice:developers file.txt   # Change owner to alice, group to developers
chown -R alice /opt/myapp/        # Recursively change owner of directory
```

#### chgrp - Change Group

```bash
chgrp developers /opt/myapp/      # Change group of directory
chgrp -R developers /opt/myapp/   # Recursively change group
```

#### sudo - Run as Superuser

```bash
sudo ls /root                     # Run ls as root
sudo useradd newuser              # Run useradd as root
sudo -i                           # Switch to root shell

# sudo configuration is at /etc/sudoers
# Edit it with: sudo visudo (NEVER edit directly with vim)
```

**Scenario-based solution (exam question type):**

> "A development server has developer1, developer2, and tester1. Source code must be accessible to developers (read+write+execute), testers get read-only. Others get nothing."

```bash
# 1. Create groups
groupadd developers
groupadd testers

# 2. Create users and assign to groups
useradd -m -G developers developer1
useradd -m -G developers developer2
useradd -m -G testers tester1

# 3. Set ownership of source directory
chown developer1:developers /opt/sourcecode/

# 4. Set permissions: owner rwx, group rwx, others nothing
chmod 770 /opt/sourcecode/

# OR if testers also need read access (as the question states):
# We need owner=rwx, developers=rwx, testers=r-x
# This requires ACLs (setfacl) for three permission levels, OR:
# Change group to developers and give 750:
chmod 750 /opt/sourcecode/
# Then add testers separately via ACL:
setfacl -m g:testers:rx /opt/sourcecode/

# 5. Verify
ls -la /opt/sourcecode/
```

---

### 3.16 Environment Variables

**What are Environment Variables:**

Environment variables are named values stored in the shell's memory that control the behavior of programs. They are like global settings for your shell session and any programs it launches.

**Common environment variables:**

| Variable | Purpose | Example value |
|---|---|---|
| PATH | Directories to search for commands | /usr/local/bin:/usr/bin:/bin |
| HOME | Current user's home directory | /home/developer1 |
| USER | Current username | developer1 |
| SHELL | Current shell | /bin/bash |
| JAVA_HOME | Java installation directory | /usr/lib/jvm/java-11 |
| EDITOR | Default text editor | vim |
| PWD | Present working directory | /home/developer1/project |

**Working with environment variables:**

```bash
# View all environment variables
env
printenv

# View a specific variable
echo $JAVA_HOME
printenv JAVA_HOME

# Set a variable for CURRENT session only (temporary)
export JAVA_HOME=/usr/lib/jvm/java-11

# Add to PATH
export PATH=$PATH:/usr/local/myapp/bin

# Verify the change
echo $PATH

# Unset a variable
unset JAVA_HOME
```

**Making environment variables PERMANENT:**

```bash
# For a specific user - add to ~/.bashrc (runs every new terminal session)
echo 'export JAVA_HOME=/usr/lib/jvm/java-11' >> ~/.bashrc
echo 'export PATH=$PATH:$JAVA_HOME/bin' >> ~/.bashrc
source ~/.bashrc    # Apply changes to current session

# For ALL users - add to /etc/environment (requires sudo)
sudo echo 'JAVA_HOME=/usr/lib/jvm/java-11' >> /etc/environment
```

**Why environment variables are useful in DevOps:**
- Store configuration without hardcoding in application code
- Same code runs in different environments (dev/test/prod) just by changing env vars
- Store secrets like database passwords and API keys without putting them in code
- CI/CD tools (Jenkins, GitHub Actions) inject env vars into builds automatically

---

### 3.17 SSH - Secure Shell

**What is SSH:**

SSH (Secure Shell) is a cryptographic network protocol for securely connecting to remote machines over an insecure network. It replaced older insecure protocols like Telnet and rlogin.

**Why SSH is preferred over Telnet:**
- All communication is **encrypted** (Telnet sends passwords in plain text)
- Supports public-key authentication (no password needed, highly secure)
- Port forwarding, tunneling, and SCP/SFTP for file transfers
- Standard for remote server administration

**Basic SSH usage:**

```bash
# Connect to a remote server with password
ssh developer1@192.168.1.2           # username@IP_address
ssh developer1@192.168.1.2 -p 2222  # Custom port (default is 22)

# Run a command on remote server without interactive login
ssh developer1@192.168.1.2 "ls /var/log"
```

**SSH Key-based Authentication (more secure than passwords):**

```bash
# Step 1: Generate an SSH key pair on your local machine
ssh-keygen -t rsa -b 4096            # Generates public/private RSA key pair
# Creates:
#   ~/.ssh/id_rsa         (PRIVATE key - keep secret, never share)
#   ~/.ssh/id_rsa.pub     (PUBLIC key - safe to share, put on servers)

# Step 2: Copy your public key to the remote server
ssh-copy-id developer1@192.168.1.2
# This appends your public key to ~/.ssh/authorized_keys on the remote server

# Step 3: Now connect without password
ssh developer1@192.168.1.2           # Uses key automatically

# Manual alternative to ssh-copy-id:
cat ~/.ssh/id_rsa.pub | ssh developer1@192.168.1.2 "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"
```

**SSH Config file (`~/.ssh/config`) for convenience:**

```
Host myserver
    HostName 192.168.1.2
    User developer1
    IdentityFile ~/.ssh/id_rsa
    Port 22
```
Now you can just type: `ssh myserver`

**SSH file permissions (critical - SSH will refuse if permissions are wrong):**

```bash
chmod 700 ~/.ssh                    # Directory: owner only
chmod 600 ~/.ssh/id_rsa             # Private key: owner read/write only
chmod 644 ~/.ssh/id_rsa.pub         # Public key: others can read
chmod 600 ~/.ssh/authorized_keys    # Authorized keys: owner only
```

**SCP - Secure Copy (file transfer over SSH):**

```bash
# Copy file FROM local TO remote
scp local_file.txt developer1@192.168.1.2:/home/developer1/

# Copy file FROM remote TO local
scp developer1@192.168.1.2:/var/log/app.log ./

# Copy entire directory recursively
scp -r ./myproject developer1@192.168.1.2:/opt/
```

**SSH Server configuration (`/etc/ssh/sshd_config`):**

```bash
# Important settings (requires sudo to edit)
Port 22                          # Change to non-standard port for security
PermitRootLogin no               # Disable root login via SSH
PasswordAuthentication no        # Force key-based auth only
AllowUsers developer1 developer2 # Whitelist specific users
```

---

## 4. PYQ Solutions (Module 1 only)

Questions are grouped by topic. Source paper is noted. Only Module 1 relevant questions are solved here.

---

### 4.1 Benefits of DevOps

**[ESE Jul-Nov 2025] Q1(i) - List any five benefits of adopting DevOps in an organization. [5M]**

Answer:

Five major benefits of adopting DevOps in an organization:

1. **Continuous delivery of software:** DevOps enables organizations to release new features, updates, and bug fixes continuously rather than in large, infrequent batches. This means customers receive value faster.

2. **Early detection and fixing of errors:** With continuous integration and automated testing at every stage, bugs are caught early in the development cycle when they are cheapest to fix, rather than discovered after deployment.

3. **Better collaboration between teams:** DevOps breaks down the traditional silo between development and operations teams. Shared responsibility and shared tools improve communication and reduce blame culture.

4. **Automated approach with less manual intervention:** Automation of build, test, and deployment processes reduces human error and saves time. Repetitive tasks are handled by tools, freeing people for higher-value work.

5. **Better efficiency, scalability, and faster time to market:** With streamlined processes and automated pipelines, organizations can respond faster to market changes, scale their infrastructure rapidly, and deliver products before competitors.

Additional benefits (use any 5): More security, enhanced recovery time, productivity gains, transparency in execution, governance with approval-based releases.

---

### 4.2 Affinity in DevOps

**[ESE Jul-Nov 2025] Q1(ii) / [ESE SVU 2020] Q1(i) - Define affinity and explain its significance in achieving high-performing teams. [5M]**

Answer:

**Definition:** Affinity in DevOps refers to the organizational principle of grouping people who work closely together based on shared goals, responsibilities, and workflows. It describes the natural alignment between Development and Operations teams - a shared ownership mindset where both teams feel responsible for the full lifecycle of a product from code to production.

**Significance for high-performing teams:**

1. **Shared ownership reduces blame:** When Dev and Ops have affinity (shared goals), production failures become a shared problem to solve together, not a finger-pointing exercise between departments.

2. **Blameless culture:** High-performing DevOps teams conduct blameless postmortems - they analyze the system and processes that led to failure, not the individuals. This creates psychological safety and encourages honest reporting of issues.

3. **Faster feedback loops:** Teams with affinity communicate openly. A developer who understands operations constraints writes more deployable code. An ops engineer who understands development pressures makes better deployment decisions.

4. **Conway's Law alignment:** Organizations tend to build systems that mirror their communication structure. Teams with strong affinity build well-integrated systems. Affinity in the team leads to affinity in the software.

5. **Reduced handoff friction:** Traditional Dev-to-Ops handoffs involve long documentation, meetings, and delays. Affinity means teams anticipate each other's needs and work proactively, eliminating handoff friction.

**In summary:** Affinity is the social glue of DevOps. High-performing teams are not just technically skilled - they are aligned in culture, goals, and responsibility. Affinity transforms two competing teams into one unified team delivering value.

---

### 4.3 Main Components of DevOps Culture

**[ESE SVU 2020] Q1(ii) - What are the main components of DevOps culture? [5M]**

Answer:

The main components of DevOps culture are:

1. **Collaboration:** Dev and Ops teams work together throughout the entire software lifecycle rather than in isolated silos. Tools like shared dashboards, chat platforms, and joint standups facilitate collaboration.

2. **Trust and Empathy:** Each team understands the other's challenges. Developers understand production constraints; Ops engineers understand release pressures. This mutual understanding prevents blame and promotes joint problem-solving.

3. **Shared Responsibility / Ownership:** The "you build it, you run it" principle means developers are responsible for their code in production, not just in dev environments. This motivates writing production-ready, observable code.

4. **Blameless Culture / Psychological Safety:** When failures occur, teams analyze systems and processes - not people. This safety encourages reporting problems early rather than hiding them.

5. **Continuous Learning and Improvement:** DevOps culture values learning from failures through postmortems, knowledge sharing, documentation, and regular retrospectives. The goal is continuous improvement, not perfection.

6. **Automation Mindset:** Manual, repetitive tasks are automated. The cultural expectation is: "if you did it twice manually, automate it the third time."

---

### 4.4 DevOps Lifecycle

**[Re-ISE] Q1 - Explain the DevOps lifecycle and illustrate how automation, collaboration, and feedback loops improve delivery speed and product reliability. Include a labeled pipeline diagram and discuss each phase briefly. [10M]**

Answer:

**The DevOps Lifecycle:**

The DevOps lifecycle is a continuous, iterative process represented as an infinity loop (figure-8). It integrates the development (left loop) and operations (right loop) sides into one unified workflow.

**Labeled Pipeline Diagram:**

```
[Development Side]              [Operations Side]

  PLAN <----------------------------+
    |                               |
    v                               |
  CODE                          MONITOR
    |                               |
    v                               |
  BUILD -----> INTEGRATE -----> DEPLOY
    |                               |
    v                               |
  TEST <------------------------OPERATE
```

**Phase-by-Phase Explanation:**

| Phase | Key Activity | Automation | Collaboration |
|---|---|---|---|
| **Plan** | Requirements, backlog, sprint planning | Jira auto-assigns tasks | Dev + Ops + Stakeholders align |
| **Code** | Write feature code, version control | Git hooks run linters | Pair programming, code review |
| **Build** | Compile, package artifacts | Maven/Gradle auto-build on commit | Dev team |
| **Test** | Unit, integration, regression tests | Selenium/JUnit auto-run | QA + Dev together |
| **Integrate** | Merge branches, CI pipeline | Jenkins triggers build + test automatically | All teams |
| **Deploy** | Release to production | CD pipeline auto-deploys approved builds | Dev + Ops shared ownership |
| **Operate** | Manage production environment | Config management (Ansible/Chef) | Ops + Dev on-call |
| **Monitor** | Track metrics, logs, alerts | Nagios/Splunk alert automatically | Feedback to Dev team |

**How automation improves delivery speed:**
- Manual build: 2-4 hours -> Automated CI pipeline: 10-15 minutes
- Manual testing: Days -> Automated test suite: Minutes
- Manual deployment: Hours + risk -> Automated CD: Minutes + rollback

**How collaboration improves reliability:**
- Shared on-call rotations mean developers experience production problems firsthand
- Joint postmortems fix root causes, not just symptoms
- Dev writes more robust code when they know they will support it in production

**How feedback loops improve quality:**
- Real-time monitoring (Nagios, Splunk) sends alerts to development teams
- A/B testing, feature flags, and user analytics feed insights back to planning
- Short sprint cycles (7 Cs) mean mistakes are corrected within days, not months

---

### 4.5 The 7 Cs of DevOps

**[Re-ISE] Q2 - Write a note on 7C in DevOps. [10M]**

Answer:

The 7 Cs of DevOps represent the continuous practices that together form a complete, uninterrupted software delivery pipeline. Each C corresponds to a phase or practice in the DevOps lifecycle.

**1. Continuous Development**
- Covers: Planning and Coding phases
- Stakeholders and requirements are gathered. The product backlog is maintained based on customer feedback and broken into smaller, manageable releases.
- Tools: Git, GitHub (distributed version control)
- Key idea: Development is not a one-time event but an ongoing process of incremental improvement.

**2. Continuous Integration (CI)**
- The most important C in the lifecycle.
- Updated code and new features are integrated into the existing codebase continuously.
- Defects are caught at each level of unit testing and the code is updated immediately.
- Code is tested before every commit, making integration a routine event rather than a crisis.
- Tools: Jenkins, Bamboo, CircleCI

**3. Continuous Testing**
- Quality analysts regularly test software for defects using Docker containers for isolated test environments.
- Some teams test before integration, others after - both approaches are valid.
- Automation testing minimizes time and effort required to get reliable results.
- In the event of a bug, code is returned to integration for correction.
- Tools: Selenium, TestNG, JUnit

**4. Continuous Deployment (CD)**
- Finished, tested code is released to production servers automatically.
- Involves configuration management to ensure proper and smooth deployment.
- Development teams deliver code and schedule server upgrades maintaining consistent configurations.
- Tools: Puppet, Chef, Ansible, Docker

**5. Continuous Feedback**
- Client behavior is routinely examined for each release.
- Structured feedback: questionnaires and surveys.
- Unstructured feedback: social media, support tickets.
- Feedback is used to prioritize the next iteration of development.

**6. Continuous Monitoring**
- Functioning and features of the application are regularly monitored to detect system faults (low memory, server unreachable, high CPU usage).
- IT staff can swiftly detect performance issues and their root causes.
- When a serious issue is found, the application goes through the complete DevOps cycle again.
- Tools: Nagios, Splunk, Munin, Ganglia

**7. Continuous Collaboration** (implied in the model)
- The cultural C that underlies all other Cs.
- Dev, Ops, QA, and business stakeholders share goals, tools, and accountability.
- Enabled through shared dashboards, joint on-call, blameless postmortems.

**Summary diagram:**

```
Continuous Development -> Continuous Integration -> Continuous Testing
       ^                                                        |
       |                                                        v
Continuous Collaboration                           Continuous Deployment
       |                                                        |
       |                                                        v
Continuous Feedback <-- Continuous Monitoring <-- (Production)
```

---

### 4.6 Goals of Development, Release, and Deployment in DevOps

**[ESE Jul-Nov 2025] Q2A(i) - What are the main goals of Development, Release, and Deployment concepts in DevOps? [5M]**

Answer:

**Development:**
- Continuously add value through features and bug fixes in short, manageable increments
- Write production-ready code from day one - not just "works on my machine" code
- Use version control, feature branches, and code reviews to maintain quality
- Goal: a steady stream of working, tested software increments

**Release:**
- Create a versioned, tested artifact that is ready and safe for production deployment
- Every release should be a routine, low-risk event (not a scheduled "big bang" deployment)
- Involves semantic versioning, release notes, and artifact storage in repositories like Nexus
- Goal: a clearly identified, immutable, deployable package that can be traced back to its source code

**Deployment:**
- Get the released artifact running in production with minimal downtime, maximum reliability, and complete repeatability
- Automated deployment pipelines eliminate human error and configuration drift
- Configuration management tools (Ansible, Puppet, Chef) ensure every server is identically configured
- Rollback plans must exist for every deployment (if something goes wrong, revert quickly)
- Goal: production that always matches the desired state, with zero-touch deployments

Together, these three concepts represent the "last mile" of the DevOps value stream - transforming developer work into running software that serves users.

---

### 4.7 Empathy and Trust in DevOps Transformations

**[ESE Jul-Nov 2025] Q2A(ii) - Analyze how empathy and trust contribute to the success of DevOps transformations. [5M]**

**[ESE Jul-Nov 2025, ISE scenario] Q2B(i) - Practical steps to build trust and empathy between Dev and Ops teams. [10M]**

Answer:

**Why Trust and Empathy are foundational:**

DevOps is fundamentally a people problem before it is a technology problem. Organizations that buy all the right tools (Jenkins, Docker, Kubernetes) but maintain a blame culture and siloed teams get "DevOps theater" - they look like they are doing DevOps but do not get the benefits.

**How Empathy contributes:**

Empathy means each team genuinely understands the pressures, constraints, and goals of the other:

- A developer who has been on-call at 3am knows how painful bad deployments are. They write more observable code (proper logging, health checks).
- An operations engineer who sits with developers during sprint planning understands why release timelines matter. They plan deployment windows more flexibly.
- Without empathy: Ops sees every release as a threat to stability. Dev sees every "not now" from Ops as obstruction. Result: infrequent, risky, fear-driven deployments.

**How Trust contributes:**

Trust means teams can act without requiring excessive approvals, documentation, and oversight:

- Developers trust that automated pipelines will catch errors before production
- Ops trusts that developers have tested code adequately before requesting deployment
- Management trusts teams to self-organize and make good decisions
- Without trust: every deployment needs a 20-page change request form, 3 committee approvals, and a 4-hour maintenance window. Speed becomes impossible.

**Practical steps to build trust and empathy:**

1. **Joint on-call rotations:** Developers participate in operations on-call. This builds immediate empathy - they feel the pain of their own bugs at 2am.

2. **Blameless postmortems:** After every incident, write a detailed incident report that focuses on what failed in the system/process, not who made the mistake. Share postmortems org-wide.

3. **Shared dashboards and observability:** Both Dev and Ops see the same production metrics in real-time. No information asymmetry = no blame asymmetry.

4. **Cross-team pairing / job shadowing:** Operations engineers shadow developers for a sprint; developers shadow operations during a deployment window.

5. **Celebrate shared successes:** When a deployment goes smoothly, recognize the entire team. When something breaks, the team owns the fix together.

6. **Defined SLOs (Service Level Objectives):** Clear, agreed-upon targets for reliability and speed give both teams a shared success metric rather than competing metrics.

**Conclusion:** Technical tools accelerate DevOps; trust and empathy make it sustainable. Organizations that invest in culture alongside tooling achieve 2-3x higher deployment frequency and 3x lower change failure rates (as documented in the State of DevOps report).

---

### 4.8 Scaling DevOps - Team Level vs Organizational Level

**[ESE Jul-Nov 2025] Q3(i) - Analyze how scaling DevOps practices differs at the team level versus the organizational level. [10M]**

Answer:

**Team Level DevOps:**

At the team level, DevOps is about the daily practices of a small (5-10 person) cross-functional team:

| Practice | Implementation at team level |
|---|---|
| Version control | Every team member commits to the same Git repository daily |
| CI/CD | Team runs its own Jenkins pipeline for its microservice |
| Testing | Team writes and maintains its own automated tests |
| Monitoring | Team gets alerts for its own service on-call |
| Retrospectives | Team conducts weekly blameless reviews |

At team level, challenges are: getting everyone to follow practices consistently, avoiding "hero" culture (one person handles everything), and automating enough to move fast.

**Organizational Level DevOps:**

Scaling DevOps to an entire organization (hundreds of teams) introduces new challenges:

| Challenge | Solution at org level |
|---|---|
| Inconsistent practices across teams | Establish "golden path" templates - standard pipelines, security policies |
| Shared infrastructure bottlenecks | Platform Engineering team builds internal tooling used by all teams |
| Security and compliance at scale | Shift security left - automated security scans in every pipeline (DevSecOps) |
| Conway's Law | Reorganize teams around products/services (not functions) to enable DevOps |
| Knowledge silos | Internal tech conferences, communities of practice (CoPs), shared wikis |
| Tool sprawl | Standardize on approved toolchain, avoid every team reinventing the wheel |

**Key differences:**

| Dimension | Team Level | Organizational Level |
|---|---|---|
| Focus | Practices (CI/CD, testing, on-call) | Culture + Structure + Governance |
| Change agents | Team lead, Scrum Master | CTO, VP Engineering, DevOps Champions |
| Speed of change | Fast (can change in a sprint) | Slow (months to years) |
| Metrics | Deployment frequency, lead time for team | DORA metrics across all teams |
| Main risk | Technical debt, missing automation | Conway's Law, organizational resistance |
| Success indicator | Team deploys daily, low incident rate | All teams deploy frequently, org-wide MTTR drops |

**DORA Metrics (DevOps Research and Assessment - key exam term):**
- Deployment Frequency: how often do you deploy?
- Lead Time for Changes: time from commit to production
- Mean Time to Recover (MTTR): how fast do you recover from failures?
- Change Failure Rate: what % of deployments cause failures?

Top-performing organizations deploy multiple times per day with MTTR under one hour.

---

### 4.9 DevOps Folk Model

**[ESE Jul-Nov 2025] Q5(i) / [ESE SVU 2020] Q5(i) - DevOps as a Folk Model. [5M]**

Answer:

**Definition:** The "Folk Model" of DevOps refers to the informal, varied, and often incomplete understandings that different people within an organization have about what DevOps is. It is the "common sense" understanding that emerges from experience and observation rather than from formal study.

**Why it exists:**

DevOps has no single, authoritative, universally agreed-upon definition. Unlike "Scrum" (which has a documented framework), DevOps emerged organically from practitioners. This means:
- Different consultants define it differently
- Tool vendors define it in terms of their products
- Managers define it in terms of outcomes they want
- Engineers define it in terms of the practices they use

**Common folk models of DevOps:**

| Stakeholder | Their Folk Model |
|---|---|
| Tool vendor | "DevOps = our CI/CD product" |
| Manager | "DevOps = faster deployments, fewer incidents" |
| Developer | "DevOps = I have to write YAML and maintain pipelines now" |
| Ops engineer | "DevOps = developers trying to do our job" |
| HR/recruiter | "DevOps = a job title, a role to hire for" |

**The problem with folk models:**

When each team in an organization operates from a different folk model, their DevOps initiatives conflict:
- Management buys automation tools expecting cultural transformation (it does not happen)
- A "DevOps team" is created as a separate silo (defeats the purpose - DevOps is about removing silos)
- Only tooling changes without process or culture changes = "DevOps theater"

**The correct model:**

DevOps is a sociotechnical system requiring simultaneous transformation of:
1. **People and Culture** (trust, empathy, shared ownership)
2. **Processes and Practices** (CI/CD, blameless postmortems, feedback loops)
3. **Technology and Tools** (automation, monitoring, configuration management)

Focusing on any one dimension without the other two leads to partial, unsustainable improvement.

**Conclusion:** Understanding DevOps as a folk model is important because it explains why so many DevOps implementations fail to deliver promised benefits. Success requires aligning the folk models across the organization around the comprehensive people-process-technology triad.

---

### 4.10 Linux File System Questions

**[Sample.pdf] Q3 - Describe the Linux Directory Structure (FHS). Explain the purpose of /etc, /var, /home, /usr, and /root directories.**

Answer:

The Linux Filesystem Hierarchy Standard (FHS) defines the directory structure and directory contents in Linux distributions. All directories originate from the root directory `/`.

**Key directories:**

| Directory | Full Name | Purpose | DevOps relevance |
|---|---|---|---|
| `/etc` | Et cetera | System-wide configuration files | Edit sshd_config, nginx.conf, crontab, /etc/passwd |
| `/var` | Variable | Data that changes during operation - logs, spool, mail | Check /var/log for application and system logs |
| `/home` | Home | User home directories - /home/alice, /home/bob | Developer workspaces, SSH keys in ~/.ssh |
| `/usr` | Unix System Resources | User programs, libraries, documentation | /usr/bin (commands), /usr/lib (libraries) |
| `/root` | Root home | Home directory of the root superuser (NOT under /home) | Root user's scripts, configs |
| `/opt` | Optional | Third-party, optional software | Jenkins, custom applications installed here |
| `/tmp` | Temporary | Files that are not preserved between reboots | Build artifacts temporarily stored here |
| `/bin` | Binaries | Essential commands needed in single-user mode | ls, cp, mv, cat, echo |
| `/proc` | Processes | Virtual filesystem - kernel and process information | /proc/cpuinfo, /proc/meminfo, /proc/PID |
| `/dev` | Devices | Device files for hardware | /dev/sda (disk), /dev/null (discard), /dev/tty (terminal) |

**Commands to navigate:**

```bash
ls /etc                         # List config files
ls /var/log                     # List log files
cat /var/log/syslog             # View system log
find /etc -name "*.conf"        # Find all config files
grep -r "ServerName" /etc/      # Search config files for a string
```

---

### 4.11 Permissions and Ownership

**[Sample.pdf] Q4 - Differentiate between file permissions and file ownership in Linux. Explain how chmod, chown, and chgrp commands are used with a suitable example.**

Answer:

**File Ownership vs File Permissions:**

| Concept | What it is | Commands | Example |
|---|---|---|---|
| **Ownership** | Who owns a file/directory (a user and a group) | chown, chgrp | alice:developers owns /opt/app |
| **Permissions** | What operations are allowed on the file for owner/group/others | chmod | rwxr-x--- |

They work together: permissions define what is allowed, ownership defines who gets those permissions.

**chmod - Change Mode (permissions):**

```bash
# Scenario: A deployment script should be executable by its owner
chmod +x deploy.sh                # Add execute bit for owner (symbolic)
chmod 755 deploy.sh               # rwxr-xr-x (octal)

# Config file: owner can write, others can only read
chmod 644 app.config              # rw-r--r--

# Sensitive file: only owner can access
chmod 600 ~/.ssh/id_rsa           # rw------- (SSH private key)

# Directory: team has full access, others have none
chmod 770 /opt/sourcecode/        # rwxrwx---
```

**chown - Change Ownership:**

```bash
# Give a file to user alice
chown alice report.txt

# Give a file to alice, assign group to developers
chown alice:developers /opt/app/

# Recursively change ownership of all files in a directory
chown -R alice:developers /opt/sourcecode/

# Verify
ls -la /opt/sourcecode/
# Output: drwxrwx--- 2 alice developers 4096 Oct 27 /opt/sourcecode/
```

**chgrp - Change Group:**

```bash
# Change just the group (when owner stays the same)
chgrp testers /opt/reports/
chgrp -R testers /opt/reports/    # Recursively
```

**Full scenario example:**

> Deploy an application to /opt/webapp/ owned by the deploy user, group devops, with full access for devops group and no access for others.

```bash
# Create user and group
groupadd devops
useradd -m -G devops deploy

# Set up directory
chown deploy:devops /opt/webapp/
chmod 770 /opt/webapp/          # rwxrwx---

# Verify
ls -la /opt/
# drwxrwx--- 2 deploy devops 4096 Oct 27 webapp/
```

---

### 4.12 Pipes and Redirection

**[Sample.pdf] Q5 - Explain stdin, stdout, and stderr in Linux. How do pipes and redirection operators work together to chain commands?**

Answer:

**Standard Streams:**

Every Linux process communicates through three standard streams:

- **stdin (0):** Standard Input - where a program reads data from. Default: keyboard. Can be redirected from a file or another command.
- **stdout (1):** Standard Output - where a program writes its normal output. Default: terminal screen. Can be redirected to a file or another command.
- **stderr (2):** Standard Error - where a program writes error messages. Default: terminal screen. Kept separate from stdout so errors can be handled independently.

**Redirection - controlling where data goes:**

```bash
# stdout to file (overwrite)
ls -la > directory_listing.txt

# stdout to file (append)
echo "Build completed at $(date)" >> build.log

# stdin from file
sort < unsorted_names.txt

# stderr to file
find / -name "nginx.conf" 2> search_errors.log

# Both stdout and stderr to same file
./deploy.sh &> deployment_log.txt
```

**Pipes - connecting commands:**

The `|` operator takes the stdout of the left command and feeds it as stdin to the right command. This creates a pipeline where data flows through multiple transformation steps.

```bash
# Step 1: Find error lines
# Step 2: Count them
# Step 3: Append count to a daily report
grep "ERROR" /var/log/app.log | wc -l >> /var/log/daily_error_count.txt
```

**Complex pipeline example (from notes):**

```bash
# Filter errors from app.log, save to file, AND display count
grep -i 'error' app.log | tee error-only.log | wc -l

# How it works:
# grep -i 'error' app.log   -> finds all ERROR lines -> stdout
# | tee error-only.log       -> writes those lines to error-only.log AND passes them on
# | wc -l                    -> counts the lines passed through and prints count
```

**Combining redirection and pipes:**

```bash
# Find .log files modified in last 24 hours, get size info, sort by size, show top 5
find /var/log -name "*.log" -mtime -1 | xargs du -h | sort -rh | head -5

# List all users sorted alphabetically, save to file
cut -d: -f1 /etc/passwd | sort > /tmp/userlist.txt
```

---

### 4.13 Package Management and SSH

**[Sample.pdf] Q6 - Differentiate between Linux package managers (apt vs yum/dnf). Explain the role of SSH keys and environment variables in automating remote Linux server connections.**

Answer:

**apt vs yum/dnf comparison:**

| Feature | apt (Debian/Ubuntu) | yum/dnf (RHEL/CentOS/Fedora) |
|---|---|---|
| Package format | .deb | .rpm |
| Low-level tool | dpkg | rpm |
| High-level tool | apt | yum (old) / dnf (modern) |
| Update package list | apt update | dnf update |
| Install package | apt install nginx | dnf install nginx |
| Remove package | apt remove nginx | dnf remove nginx |
| Search package | apt search nginx | dnf search nginx |
| Repo config | /etc/apt/sources.list | /etc/yum.repos.d/ |
| Dependency resolution | Automatic | Automatic |

**SSH Keys in automation:**

In DevOps, automation scripts must connect to servers without human interaction (no password prompts). SSH key-based authentication solves this:

```bash
# 1. Generate key pair on CI server (Jenkins, GitHub Actions runner)
ssh-keygen -t rsa -b 4096 -N "" -f ~/.ssh/deploy_key
# -N "" means no passphrase (necessary for automation)

# 2. Install public key on all target servers
ssh-copy-id -i ~/.ssh/deploy_key.pub deploy@server1.example.com
ssh-copy-id -i ~/.ssh/deploy_key.pub deploy@server2.example.com

# 3. Automation script connects with no interaction
ssh -i ~/.ssh/deploy_key deploy@server1.example.com "docker pull myapp:latest && docker restart myapp"
```

Without key-based auth, automation scripts would need to embed passwords in plaintext (a security risk) or use expect scripts (fragile).

**Environment variables in automation:**

Environment variables allow scripts to be environment-agnostic:

```bash
# Instead of hardcoding server details:
SERVER_IP=192.168.1.10          # Hardcoded - BAD
# Use environment variables:
SERVER_IP=$DEPLOY_SERVER        # From environment - GOOD

# Jenkins injects build-specific env vars:
echo "Deploying build $BUILD_NUMBER to $DEPLOY_SERVER"
ssh -i $SSH_KEY deploy@$DEPLOY_SERVER "
    export APP_ENV=$TARGET_ENV
    export DB_HOST=$DATABASE_HOST
    docker run -e APP_ENV -e DB_HOST myapp:$BUILD_NUMBER
"
```

**Combined workflow in DevOps automation:**

```bash
#!/bin/bash
# deploy.sh - called by Jenkins pipeline

SSH_KEY=/var/jenkins_home/.ssh/deploy_key
SERVERS="web01 web02 web03"
IMAGE_TAG=$1

for server in $SERVERS; do
    ssh -i $SSH_KEY -o StrictHostKeyChecking=no deploy@$server \
        "docker pull myregistry/myapp:$IMAGE_TAG && \
         docker stop myapp && \
         docker run -d --name myapp -p 80:8080 \
         -e DB_HOST=$DB_HOST \
         -e APP_SECRET=$APP_SECRET \
         myregistry/myapp:$IMAGE_TAG"
    echo "Deployed to $server successfully"
done
```

---

### 4.14 Virtualization - VM Scenario

**[Sample.pdf] Q2 - A college wants to provide Linux environments to 50 students for practicing DevOps tools. Explain how virtualization can solve this, compare physical vs virtual machines, suggest VMware/VirtualBox use.**

Answer:

**How virtualization solves the problem:**

Instead of purchasing 50 physical servers (expensive, wasteful), the college can:
1. Purchase 5-10 powerful physical servers
2. Install a Type 2 hypervisor (VirtualBox) or Type 1 (VMware ESXi) on them
3. Create multiple Virtual Machines on each physical server
4. Each student gets their own isolated Linux VM with their own filesystem, processes, and network

This reduces hardware cost by 80-90% while providing each student a completely isolated environment.

**Physical Machine vs Virtual Machine:**

| Aspect | Physical Machine | Virtual Machine |
|---|---|---|
| Hardware | Dedicated, real | Virtualized (shared with other VMs) |
| Setup time | Days-weeks | Minutes (clone a template VM) |
| Cost | High per student | Low - multiple VMs per server |
| Isolation | Complete | Strong (hypervisor enforces boundaries) |
| Portability | Cannot move easily | VM is a file - copy/snapshot/migrate |
| Resource utilization | Often underutilized | Efficiently shared |
| If machine fails | Only that student affected | Can affect multiple students |

**VirtualBox for college lab (recommendation):**

VirtualBox (free, open-source) is ideal:
1. Download VirtualBox at virtualbox.org
2. Create a "template" Ubuntu VM with DevOps tools pre-installed (Git, Docker, Jenkins)
3. Export template as .ova file
4. Each student imports the .ova - their own copy is ready in 5 minutes
5. Students can snapshot their VM before labs (instant restore if something breaks)

**Advantages for DevOps practice:**
- Students can break things without consequences (snapshot + restore)
- Isolated networks - students can practice firewall rules without affecting others
- Same environment for everyone - no "works on my machine" issues in class
- Easy cleanup - delete the VM when the lab is over

**Limitations:**
- All VMs share host CPU/RAM - if one student does heavy builds, others slow down
- VM disk images consume significant host storage (10-20GB per student VM)
- Nested virtualization needed to run Docker inside VMs (may be slow)
- Not as lightweight as containers for simple practice

---

### 4.15 ISE Questions

**[ISE_DEVOPS] - A startup is struggling with unstable production releases. Builds pass in Jenkins but fail in deployment. Analyze possible causes and propose a DevOps solution. [10M]**

Answer:

**Analysis - Possible Causes:**

1. **Environment mismatch:** The Jenkins build server has different library versions, Java versions, or OS than the production server. Code compiles in one environment, fails in another.

2. **Missing configuration files:** Production requires environment-specific config files (database URLs, API keys, connection strings) that are not present in the deployment package.

3. **Missing dependency in production:** Jenkins might have global packages installed on the build server that are assumed but not explicitly declared as dependencies. Production servers do not have these.

4. **Infrastructure drift:** Production servers have been manually patched/modified over time and are no longer in a known good state. Different servers in the same "production pool" have different configurations.

5. **Hardcoded values:** Code contains hardcoded development/test values (database IPs, port numbers) that are invalid in production.

6. **Race conditions in deployment scripts:** Deployment scripts assume sequential startup of services, but production might start them in a different order.

**DevOps-based solution:**

1. **Containerize with Docker:** Package the application with ALL its dependencies into a Docker image. The same image runs identically in Jenkins (CI) and production (CD). Environment differences become impossible.

   ```dockerfile
   FROM openjdk:11-jre
   COPY target/app.jar /app/app.jar
   ENTRYPOINT ["java", "-jar", "/app/app.jar"]
   ```

2. **Infrastructure as Code (Ansible/Terraform):** Define production server configuration as code. Every deployment uses the exact same server configuration. Drift becomes detectable and correctable.

3. **Configuration externalization:** Use environment variables or a secrets manager (Vault, AWS SSM) for all environment-specific values. The application reads `DB_HOST` from env vars, not from a hardcoded file.

4. **Staging environment:** Add a staging environment to the pipeline that is identical to production. If deployment passes staging, production should succeed.

   ```
   Jenkins -> Build -> Test -> Deploy to Staging -> Smoke Test -> Deploy to Production
   ```

5. **Automated smoke tests after deployment:** Add post-deployment health checks. If the application fails a health check within 60 seconds of deployment, automatically roll back.

6. **Blameless postmortem:** For every failed deployment, document: what failed, why it failed, what the system allowed to happen, and what change will prevent recurrence.

---

**[ISE_DEVOPS] - Compare the Old View and New View of software delivery. Which is more relevant in today's IT industry? Justify. [10M]**

Answer: (See section 3.8 comparison table above - expand with justification)

**Justification for New View being more relevant:**

Modern software systems are too complex for the Old View to work:

1. A single web request may touch 50+ microservices. When something fails, a single "root cause" often does not exist - it is the interaction of multiple normal conditions.

2. The Old View discourages people from reporting problems (fear of blame). This causes small issues to escalate into major outages. Companies using the New View (blameless culture) have faster MTTR because people report and escalate without fear.

3. The velocity demanded by modern business (deploy 10 times per day) requires automation and trust. Old View gate-keeping processes make this impossible.

4. Case studies: Google's SRE (Site Reliability Engineering) practices, Netflix's Chaos Engineering, and Amazon's deployment pipeline are all based on New View principles. These are the most reliable large-scale systems in the world.

**Conclusion:** The New View is the only practical approach for organizations that need to move fast and maintain reliability simultaneously.

---

### 4.16 Environment Variables Scenario

**[Sample.pdf] Q6 - A Java application requires JAVA_HOME and PATH to be configured before execution.**

Answer:

```bash
# 1. What are environment variables?
# Named key=value pairs stored in shell memory that programs can read.
# Used to configure behavior without hardcoding values in source code.

# 2. Check current value of JAVA_HOME
echo $JAVA_HOME
printenv JAVA_HOME
# If empty, JAVA_HOME is not set

# 3. Find where Java is installed
which java                           # Output: /usr/bin/java
readlink -f $(which java)            # Follow symlinks to actual path
# Example: /usr/lib/jvm/java-11-openjdk-amd64/bin/java

# 4. Temporarily set JAVA_HOME (this session only)
export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64
export PATH=$PATH:$JAVA_HOME/bin

# 5. Verify
echo $JAVA_HOME
java -version                        # Should work now

# 6. Make it permanent (add to ~/.bashrc)
echo 'export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64' >> ~/.bashrc
echo 'export PATH=$PATH:$JAVA_HOME/bin' >> ~/.bashrc
source ~/.bashrc                     # Apply to current session

# 7. Why environment variables are useful in DevOps:
# - Same codebase runs in dev, test, prod by changing env vars
# - Secrets (passwords, API keys) stored in env vars, not committed to Git
# - CI/CD tools inject environment-specific vars automatically per pipeline stage
# - Containerized apps read all config from env vars (12-factor app principle)
```

---

### 4.17 SSH Administration

**[Sample.pdf] Q7 - A DevOps engineer needs to remotely access a Linux cloud server. Explain SSH for remote administration.**

Answer:

**What SSH provides:**
- Encrypted command-line access to remote Linux servers
- Secure file transfer (SCP, SFTP)
- Port forwarding and tunneling
- Key-based authentication for automated scripts (no password prompts)

**General SSH command:**
```bash
ssh username@IP_address
ssh username@IP_address -p PORT_NUMBER    # If not default port 22
ssh -i /path/to/private_key username@IP_address    # With specific key

# Example:
ssh devops@203.0.113.45
ssh -i ~/.ssh/cloud_key.pem ubuntu@203.0.113.45    # AWS EC2 style
```

**Role of username, IP address, and authentication:**

- **Username:** Identifies which user account on the remote server to log into. The remote server must have this user account.
- **IP address:** The network address of the remote server. Could also be a hostname if DNS is configured.
- **Authentication:** Two methods:
  - Password: User types password at prompt. Convenient but less secure.
  - Key-based: Local machine presents private key; remote server verifies against stored public key. No password needed. Required for automation.

**Why SSH is preferred over insecure alternatives:**

| Feature | SSH | Telnet/rlogin |
|---|---|---|
| Encryption | All data encrypted | Plaintext - passwords visible on network |
| Authentication | Password + key-based | Password only |
| Integrity | Data cannot be tampered with | No integrity checks |
| Port forwarding | Supported | Not supported |
| Standard | Universal in DevOps | Obsolete, should not be used |

**Common administrative tasks via SSH:**
```bash
# Check server disk space
ssh deploy@server "df -h"

# View live logs
ssh deploy@server "tail -f /var/log/app.log"

# Restart a service
ssh deploy@server "sudo systemctl restart nginx"

# Run a deployment script
ssh -i ~/.ssh/deploy_key deploy@server "bash /opt/scripts/deploy.sh v1.2.3"
```

---

*End of DevOps_Mod_1.md*
