# Linux Fundamentals for DevOps Engineers

# Class 1 – Linux Basics, File Management & Package Management

---

# 1. Introduction

## Why Linux is Important for DevOps

Linux is the backbone of modern cloud computing and DevOps practices. Most servers, containers, and cloud platforms run on Linux.

### Why DevOps Engineers Must Learn Linux

* Most production servers run Linux.
* Cloud platforms such as AWS, Azure, and GCP heavily use Linux.
* Container technologies like Docker are built on Linux features.
* Kubernetes nodes typically run Linux.
* Automation and scripting are easier using Linux command-line tools.
* CI/CD tools often execute builds and deployments on Linux servers.

### Real-World Examples

* Deploying applications on AWS EC2 instances.
* Managing Kubernetes clusters.
* Running Jenkins build servers.
* Configuring Nginx web servers.
* Monitoring Linux-based production environments.

---

## Where Linux is Used

Linux is used almost everywhere in modern IT infrastructure.

### Common Usage Areas

| Area             | Example            |
| ---------------- | ------------------ |
| Cloud Computing  | AWS, Azure, GCP    |
| Web Servers      | Nginx, Apache      |
| Containers       | Docker             |
| Orchestration    | Kubernetes         |
| Databases        | MySQL, PostgreSQL  |
| Networking       | Routers, Firewalls |
| Embedded Systems | IoT Devices        |
| Mobile OS        | Android            |

---

## Learning Objectives

By the end of this class, you should be able to:

* Understand Linux fundamentals.
* Connect to Linux servers.
* Install and manage software packages.
* Navigate Linux file systems.
* Create, modify, and delete files.
* Manage services.
* Use the VI editor.
* Perform common administration tasks.

---

# 2. What is Linux?

## Definition

Linux is an open-source operating system kernel created by Linus Torvalds in 1991.

An operating system acts as a bridge between users, applications, and computer hardware.

### Example Operating Systems

* Windows
* macOS
* Linux

---

## Features of Linux

### Open Source

Source code is publicly available.

#### Why Needed?

* Anyone can inspect and improve the code.
* No vendor lock-in.
* Large community support.

---

### Secure

Linux provides strong security mechanisms.

#### Why Needed?

* Protects servers from unauthorized access.
* Supports permissions and access controls.
* Frequently updated by the community.

---

### Stable

Linux systems can run for months or years without rebooting.

#### Why Needed?

Production systems require high uptime and reliability.

---

### Multi-user

Multiple users can access the same system simultaneously.

#### Why Needed?

Useful in enterprise environments where many administrators and applications use the same server.

---

### CLI Based

CLI stands for Command Line Interface.

#### Why Needed?

* Faster administration.
* Easy automation.
* Better remote management.
* Essential for DevOps automation.

---

### Highly Customizable

Linux can be modified according to business requirements.

#### Why Needed?

Different workloads require different configurations.

Example:

* Web servers
* Database servers
* Kubernetes worker nodes

---

# 3. Linux Architecture

## Architecture Overview

```text
User Applications
        │
      Shell
        │
     Kernel
        │
    Hardware
```

---

## Components

### User Applications

Programs used by users.

Examples:

* Chrome
* VS Code
* Nginx
* Jenkins

#### Why Needed?

Applications perform business tasks.

---

### Shell

The shell acts as an interface between users and the kernel.

Examples:

* Bash
* Zsh
* Sh

#### Why Needed?

Allows users to execute commands and automate tasks.

---

### Kernel

The core component of Linux.

#### Why Needed?

Manages communication between software and hardware.

---

## Kernel Responsibilities

### Process Management

Manages running programs.

#### Why Needed?

Ensures applications receive CPU resources.

Example:

```bash
ps -ef
top
```

---

### Memory Management

Controls RAM usage.

#### Why Needed?

Prevents one application from consuming all memory.

---

### Storage Management

Manages disks and file systems.

#### Why Needed?

Provides reliable data storage and retrieval.

---

### Networking

Handles network communication.

#### Why Needed?

Required for servers to communicate over the internet.

---

### Security

Enforces permissions and access control.

#### Why Needed?

Protects data and systems.

---

### User Management

Handles user accounts and permissions.

#### Why Needed?

Controls who can access resources.

---

### IPC (Inter-Process Communication)

Allows processes to communicate.

#### Why Needed?

Applications often need to exchange data.

---

### cgroups (Control Groups)

Limits resource usage.

#### Why Needed?

Used by Docker and Kubernetes to control CPU and memory consumption.

---

### Namespaces

Provide process isolation.

#### Why Needed?

Fundamental technology behind containers.

Example:

Docker containers use namespaces to isolate applications.

---

# 4. Linux Distributions

A Linux distribution is a complete operating system built around the Linux kernel.

---

## Popular Linux Distributions

| Distribution | Package Manager |
| ------------ | --------------- |
| Ubuntu       | apt             |
| Debian       | apt             |
| CentOS       | yum             |
| RHEL         | yum             |
| Fedora       | dnf             |

---

## Why Different Distributions Exist

Different organizations have different requirements.

### Examples

* Ubuntu → Beginner-friendly
* RHEL → Enterprise support
* Fedora → Latest features
* Debian → Stability

---

# 5. Connecting to a Linux Server

## SSH (Secure Shell)

SSH allows secure remote access to Linux servers.

### Why Needed?

DevOps engineers rarely work directly on physical servers.

Remote administration is performed through SSH.

---

## Authentication Methods

### Password Authentication

Uses username and password.

#### Drawback

Less secure.

---

### SSH Key Authentication

Uses public-private key pairs.

#### Why Needed?

More secure and commonly used in production environments.

---

### Token-Based Authentication

Uses temporary access tokens.

#### Why Needed?

Improves security in cloud environments.

---

### Passwordless Authentication

Automated access without manual password entry.

#### Why Needed?

Required for automation pipelines.

---

## SSH Example

```bash
chmod 400 key.pem
```

### Why?

Restricts file permissions so only the owner can read the key.

---

```bash
ssh -i key.pem ubuntu@<SERVER_IP>
```

### Why?

Connects securely to a remote Linux server.

---

# 6. Package Management

Package managers install, update, and remove software.

---

## Become Root User

```bash
sudo -i
```

### Why Needed?

Administrative tasks require elevated privileges.

---

## Update Repository Metadata

```bash
apt update
```

### Why Needed?

Downloads the latest package information from repositories.

Always run before installing packages.

---

## Install Software

### Install Git

```bash
apt install git -y
```

#### Why?

Git is used for version control.

---

### Install Nginx

```bash
apt install nginx -y
```

#### Why?

Nginx is a popular web server and reverse proxy.

---

### Install Java

```bash
apt install openjdk-17-jre -y
```

#### Why?

Required to run Java applications such as Jenkins.

---

## Upgrade Packages

```bash
apt upgrade
```

### Why Needed?

Applies security patches and software updates.

---

## Remove Packages

```bash
apt remove git
```

### Why Needed?

Removes software that is no longer required.

---

## Find Installation Path

```bash
which git
```

```bash
which nginx
```

### Why Needed?

Shows the location of executable files.

Example Output:

```bash
/usr/bin/git
```

---

# 7. Service Management

Services are background processes that keep running.

Examples:

* Nginx
* Jenkins
* Docker

---

## Check Status

```bash
systemctl status nginx
```

### Why?

Verifies whether the service is running.

---

## Start Service

```bash
systemctl start nginx
```

### Why?

Starts the service immediately.

---

## Stop Service

```bash
systemctl stop nginx
```

### Why?

Stops the service.

---

## Restart Service

```bash
systemctl restart nginx
```

### Why?

Applies configuration changes.

---

## Enable Service

```bash
systemctl enable nginx
```

### Why?

Starts the service automatically after reboot.

---

## Disable Service

```bash
systemctl disable nginx
```

### Why?

Prevents automatic startup.

---

# 8. Linux Navigation

## Print Working Directory

```bash
pwd
```

### Why?

Shows the current directory.

---

## Change Directory

```bash
cd
```

### Why?

Moves between directories.

---

### Root Directory

```bash
cd /
```

---

### Home Directory

```bash
cd ~
```

---

### Parent Directory

```bash
cd ..
```

---

# 9. Listing Files

## List Files

```bash
ls
```

### Why?

Displays files and directories.

---

## Long Listing

```bash
ll
```

### Why?

Shows permissions, owner, size, and modification date.

---

## Show Hidden Files

```bash
ls -a
```

### Why?

Displays hidden files beginning with a dot (`.`).

Example:

```bash
.bashrc
.gitconfig
```

---

# 10. File Operations

## Create File

```bash
touch file.txt
```

### Why?

Creates an empty file.

---

## Write Content

```bash
echo "Hello" > file.txt
```

### Why?

Creates or overwrites content.

---

## Append Content

```bash
echo "New Line" >> file.txt
```

### Why?

Adds content without removing existing data.

---

## View Content

```bash
cat file.txt
```

### Why?

Displays file contents.

---

## Rename File

```bash
mv old.txt new.txt
```

### Why?

Renames or moves files.

---

## Delete File

```bash
rm file.txt
```

### Why?

Removes files.

---

## Force Delete

```bash
rm -f file.txt
```

### Why?

Deletes without confirmation.

Use carefully.

---

# 11. Directory Operations

## Create Directory

```bash
mkdir mydir
```

### Why?

Creates a new directory.

---

## Rename Directory

```bash
mv olddir newdir
```

### Why?

Renames a directory.

---

## Delete Directory

```bash
rm -rf mydir
```

### Why?

Deletes a directory and all contents recursively.

⚠️ Extremely dangerous command. Verify before execution.

---

# 12. VI Editor

VI is one of the most commonly available text editors in Linux.

DevOps engineers frequently use it to edit configuration files.

---

## Open File

```bash
vi file.txt
```

### Why?

Creates or opens a file for editing.

---

## Enter Insert Mode

```bash
i
```

### Why?

Allows text editing.

---

## Save and Exit

```bash
Esc :wq
```

### Why?

Saves changes and exits.

---

## Exit Without Saving

```bash
Esc :q!
```

### Why?

Discards changes and exits.

---

# Summary

In this class, you learned:

* Linux fundamentals
* Linux architecture
* Linux distributions
* SSH connectivity
* Package management
* Service management
* File and directory operations
* Linux navigation
* VI editor basics

These skills form the foundation for advanced DevOps topics such as Docker, Kubernetes, CI/CD, Cloud Computing, Infrastructure as Code (IaC), and Monitoring.
