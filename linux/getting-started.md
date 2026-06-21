# Install Ubuntu on Windows Using Microsoft Store (Recommended)

## Prerequisites

* Windows 10 (Version 2004 or later) or Windows 11
* Administrator access
* Internet connection

---

## Step 1: Enable Windows Subsystem for Linux (WSL)

Open **PowerShell** as Administrator and run:

```powershell
wsl --install
```

If WSL is already installed, you can skip to the next step.

Restart your computer if prompted.

---

## Step 2: Open Microsoft Store

1. Press the **Windows** key.
2. Search for **Microsoft Store**.
3. Open the application.

---

## Step 3: Search for Ubuntu

In the Microsoft Store search bar, search for:

```
Ubuntu
```

You will see versions such as:

* Ubuntu
* Ubuntu 24.04 LTS
* Ubuntu 22.04 LTS

**Recommendation:** Install the latest **LTS (Long-Term Support)** version (for example, Ubuntu 24.04 LTS).

---

## Step 4: Install Ubuntu

Click **Get** or **Install** and wait for the download to complete.

---

## Step 5: Launch Ubuntu

After installation:

* Click **Open**, or
* Search for **Ubuntu** from the Start Menu.

The first launch may take a few minutes to complete the initial setup.

---

## Step 6: Create Your Linux User

Ubuntu will prompt you to create:

* Username
* Password

Example:

```text
Enter new UNIX username: praveen
New password:
Retype new password:
```

This user will become your default Linux user.

---

## Step 7: Update Ubuntu

Run:

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Step 8: Verify Installation

Check the Ubuntu version:

```bash
lsb_release -a
```

Check the Linux kernel:

```bash
uname -r
```

From PowerShell, verify WSL:

```powershell
wsl --status
```

List installed distributions:

```powershell
wsl -l -v
```

Expected output:

```text
NAME      STATE      VERSION
Ubuntu    Running    2
```
