Linux Fundamentals for DevOps Engineers
Class 1 – Linux Basics, File Management & Package Management
1. Introduction
Why Linux is important for DevOps
Where Linux is used
Learning objectives
2. What is Linux?
Definition
Features
Open Source
Secure
Stable
Multi-user
CLI Based
Highly Customizable

Examples of Operating Systems

Windows
macOS
Linux
3. Linux Architecture

Linux Architecture

User Applications
        │
      Shell
        │
     Kernel
        │
    Hardware

Kernel Responsibilities

Process Management
Memory Management
Storage Management
Networking
Security
User Management
IPC
cgroups
Namespaces
4. Linux Distributions
Distribution	Package Manager
Ubuntu	apt
Debian	apt
CentOS	yum
RHEL	yum
Fedora	dnf
5. Connecting to Linux Server

Introduction to SSH

Authentication Methods

Password
SSH Keys
Token
Passwordless

SSH Example

chmod 400 key.pem

ssh -i key.pem ubuntu@<SERVER_IP>
6. Package Management

Become Root

sudo -i

Update Repository

apt update

Install Software

apt install git -y
apt install nginx -y
apt install openjdk-17-jre -y

Upgrade Packages

apt upgrade

Remove Package

apt remove git

Find Installation Path

which git
which nginx
7. Service Management

Service Commands

systemctl status nginx
systemctl start nginx
systemctl stop nginx
systemctl restart nginx
systemctl enable nginx
systemctl disable nginx
8. Linux Navigation
pwd
cd
cd /
cd ~
cd ..
9. Listing Files
ls
ll
ls -a
10. File Operations
touch file.txt

echo "Hello" > file.txt

echo "New Line" >> file.txt

cat file.txt

mv old.txt new.txt

rm file.txt

rm -f file.txt
11. Directory Operations
mkdir mydir

mv olddir newdir

rm -rf mydir
12. VI Editor

Open File

vi file.txt

Insert Mode

i

Save

Esc :wq

Exit

Esc :q!
