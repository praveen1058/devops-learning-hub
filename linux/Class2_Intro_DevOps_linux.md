# DevOps, CI/CD, Linux Fundamentals, and Server Deployment

### Example: ApnaShop E-Commerce Platform

---

# 1. What is DevOps?

**DevOps** is a culture and methodology that combines **Development (Dev)** and **Operations (Ops)** teams to deliver software faster, more reliably, and with better quality.

While **Agile** focuses on developing software quickly through sprints, **DevOps extends Agile** by automating testing, deployment, monitoring, and infrastructure management.

## Agile vs DevOps

| Agile                          | DevOps                                       |
| ------------------------------ | -------------------------------------------- |
| Focuses on Development         | Focuses on Development + Operations          |
| Delivers code quickly          | Delivers code and deployments quickly        |
| Sprint-based development       | Continuous delivery and monitoring           |
| Ends after development/testing | Continues through deployment and maintenance |

---

# 2. DevOps Workflow for ApnaShop

Suppose ApnaShop hires developers to build an e-commerce platform.

### Traditional Approach

```text
Developer
    ↓
Writes Code
    ↓
Manual Testing
    ↓
Manual Deployment
    ↓
Production Server
```

Problems:

* Slow deployment
* Human errors
* Downtime during releases
* Difficult rollback

---

### DevOps Approach

```text
Developer
    ↓
Git Repository
    ↓
CI Pipeline
    ↓
Automated Testing
    ↓
Build Artifact
    ↓
CD Pipeline
    ↓
Staging Server
    ↓
Production Server
```

Benefits:

* Faster releases
* Reduced human errors
* Automated testing
* Easier rollback
* Continuous monitoring

---

# 3. What is CI/CD?

CI/CD is the backbone of modern DevOps practices.

---

## Continuous Integration (CI)

Developers frequently merge code into a shared repository.

Every code commit automatically triggers:

* Code Validation
* Unit Testing
* Security Scanning
* Build Process

### Example

Developer adds a new "Wishlist" feature.

```text
Git Push
    ↓
Run Tests
    ↓
Build Application
    ↓
Generate Artifact
```

If tests fail, deployment stops automatically.

---

## Continuous Delivery (CD)

After CI succeeds, the application is automatically prepared for deployment.

```text
Build Success
      ↓
Deploy to Staging
      ↓
Approval
      ↓
Deploy to Production
```

---

## Continuous Deployment

An advanced form of CD where deployment to production happens automatically.

```text
Code Commit
      ↓
CI Pipeline
      ↓
Tests Passed
      ↓
Auto Deploy Production
```

No manual intervention is required.

---

# 4. Real-World ApnaShop Deployment Flow

```text
Developer
    ↓
GitHub Repository
    ↓
Jenkins / GitHub Actions
    ↓
Build Docker Image
    ↓
Push to Container Registry
    ↓
Deploy to Linux Server
    ↓
Customers Access ApnaShop
```

Popular DevOps Tools:

| Category        | Tools                              |
| --------------- | ---------------------------------- |
| Version Control | Git, GitHub, GitLab                |
| CI/CD           | Jenkins, GitHub Actions, GitLab CI |
| Containers      | Docker                             |
| Orchestration   | Kubernetes                         |
| Monitoring      | Prometheus, Grafana                |
| Cloud           | AWS, Azure, GCP                    |

---

# 5. Why Do We Need Servers (Machines)?

Developers write code on their laptops.

Customers cannot access applications running on a developer's laptop.

Therefore, the application must be deployed to a server that is:

* Always available (24/7)
* Connected to the internet
* Secure
* Scalable

### Example

```text
Developer Laptop
      ↓
Deploy
      ↓
Linux Server
      ↓
Internet
      ↓
Customers
```

---

# 6. Why Linux is Preferred Over Windows Servers

Most production applications run on Linux.

## Comparison

| Feature           | Linux             | Windows          |
| ----------------- | ----------------- | ---------------- |
| Cost              | Mostly Free       | License Required |
| Performance       | High              | Moderate         |
| Security          | Strong            | Good             |
| Resource Usage    | Low               | Higher           |
| Automation        | Excellent         | Limited          |
| Cloud Support     | Industry Standard | Less Common      |
| Docker/Kubernetes | Native Support    | Less Preferred   |

---

## Why ApnaShop Uses Linux

* Lower server cost
* Better performance
* Easier automation
* Better container support
* Industry standard for cloud deployments

---

# 7. What is an Operating System (OS)?

An **Operating System (OS)** is software that manages computer hardware and software resources.

It acts as a bridge between users/applications and hardware.

## Examples

* Linux
* Windows
* macOS
* Android
* iOS

### Diagram

```text
Applications
      ↓
Operating System
      ↓
Hardware
```

---

# 8. What is a Kernel?

The **Kernel** is the core component of an Operating System.

Responsibilities:

* Memory Management
* Process Management
* CPU Scheduling
* Device Management
* Security Controls

### Diagram

```text
Applications
      ↓
Operating System
      ↓
Kernel
      ↓
Hardware
```

Think of the Kernel as the "brain" of the operating system.

---

# 9. What is a Device Driver?

A **Driver** is software that allows the Operating System to communicate with hardware devices.

Examples:

* Keyboard Driver
* Mouse Driver
* Printer Driver
* Network Driver
* GPU Driver

### Flow

```text
Application
      ↓
Operating System
      ↓
Driver
      ↓
Hardware Device
```

Without drivers, the OS cannot properly use hardware devices.

---

# 10. What is a Directory?

A **Directory** is a folder used to organize files and subdirectories.

Example:

```text
Projects
│
├── ApnaShop
│   ├── backend
│   ├── frontend
│   └── database
│
└── Documents
```

Directories help maintain a structured file system.

---

# 11. Important Linux Directories

Linux follows a standard directory structure.

## Root Directory

```text
/
```

Everything starts from the root directory.

---

## /bin

Contains essential system commands.

Examples:

```bash
ls
cp
mv
cat
```

---

## /etc

Stores configuration files.

Examples:

```text
/etc/nginx
/etc/ssh
/etc/passwd
```

---

## /home

Stores user data.

Example:

```text
/home/devops
/home/developer
```

---

## /root

Home directory of the root user.

```text
/root
```

---

## /var

Stores variable data.

Examples:

```text
Logs
Cache
Application Data
```

Common location:

```text
/var/log
```

---

## /tmp

Temporary files.

```text
/tmp
```

---

## /usr

Installed software and libraries.

```text
/usr/bin
/usr/lib
```

---

## /opt

Third-party applications.

Example:

```text
/opt/jenkins
/opt/tomcat
```

---

## /dev

Represents hardware devices.

Examples:

```text
/dev/sda
/dev/null
```

---

## /proc

Provides information about running processes and the Linux kernel.

Example:

```text
/proc/cpuinfo
/proc/meminfo
```

---

# Linux Directory Structure

```text
/
├── bin
├── boot
├── dev
├── etc
├── home
├── opt
├── proc
├── root
├── tmp
├── usr
└── var
```

---

# Summary

For ApnaShop:

1. Developers build features using Agile practices.
2. DevOps automates testing, deployment, and monitoring.
3. CI/CD pipelines automatically build and deploy applications.
4. Applications are deployed on servers instead of developer laptops.
5. Linux is preferred because it is fast, secure, scalable, and cost-effective.
6. The Operating System manages hardware and software.
7. The Kernel is the core of the OS.
8. Drivers allow communication with hardware devices.
9. Directories organize files within Linux.
10. Understanding Linux fundamentals is essential for every DevOps Engineer.
