# Install Ubuntu on Windows using WSL (Beginner's Guide)

A step-by-step guide to install **Ubuntu on Windows 10/11** using **Windows Subsystem for Linux (WSL)** without dual booting or using a virtual machine.

## 📌 Prerequisites

Before you begin, make sure you have:

* Windows 10 or Windows 11
* Internet connection
* Administrator privileges

---

## 💡 What is WSL?

**Windows Subsystem for Linux (WSL)** allows you to run a Linux environment directly on Windows without installing a separate operating system or virtual machine.

With WSL, you can:

* Run Linux commands
* Install development tools
* Write and test code
* Use Ubuntu alongside Windows

---

# 🚀 Installation Steps

## Step 1: Enable WSL

1. Open the **Start Menu**.
2. Search for **Turn Windows features on or off**.
3. Open the application.
4. Enable the following features:

* ✅ Windows Subsystem for Linux
* ✅ Virtual Machine Platform

5. Click **OK**.
6. Restart your computer when prompted.

> **Note:** These features are required for WSL 2.

---

## Step 2: Install Ubuntu

Open **Command Prompt** or **PowerShell** as **Administrator**.

Run the following command:

```bash
wsl --install -d Ubuntu
```

Press **Enter**.

Windows will automatically:

* Download Ubuntu
* Install WSL
* Configure Ubuntu

Restart your PC if prompted.

> **Note:** `-d Ubuntu` installs the default Ubuntu distribution.

---

## Step 3: Launch Ubuntu

### Method 1: Using Command Prompt or PowerShell

Run:

```bash
wsl -d Ubuntu
```

The first time you launch Ubuntu, you'll be asked to create:

* Username
* Password

After setup, Ubuntu is ready to use.

---

### Method 2: Using the Start Menu

1. Press the **Windows** key.
2. Search for **Ubuntu**.
3. Open the Ubuntu application.

The first launch may take a few moments while Ubuntu completes its initial setup.

---

# 🛠️ Alternative: Install Ubuntu from Microsoft Store

If the command below doesn't work:

```bash
wsl --install -d Ubuntu
```

You can install Ubuntu manually.

### Steps

1. Open **Microsoft Store**.
2. Search for **Ubuntu**.
3. Choose one of the available versions, such as:

   * Ubuntu 24.04 LTS
   * Ubuntu 22.04 LTS
   * Ubuntu 20.04 LTS
   * Ubuntu Preview
4. Click **Get**.
5. Wait for the installation to complete.
6. Launch Ubuntu from the Start Menu.

---

# 🧪 Verify the Installation

Open Ubuntu and try the following commands:

```bash
ls
```

Lists files in the current directory.

```bash
pwd
```

Displays the current directory path.

```bash
sudo apt update
```

Updates the Ubuntu package list.

---

# 📚 What You Can Do with Ubuntu on WSL

After installation, you can:

* Learn Linux commands
* Install programming languages
* Use Git and GitHub
* Develop Python, Java, Node.js, C++, and more
* Run Linux development tools
* Practice shell scripting

---

# 📺 Video Tutorial

Prefer watching instead of reading?

Watch the complete step-by-step tutorial on YouTube:

> **How to Install Ubuntu on Windows using WSL**



---

# 🤝 Contributing

Contributions are welcome!

If you'd like to improve this guide, feel free to:

* Fork the repository
* Create a new branch
* Make your changes
* Submit a Pull Request

---

# ⭐ Support

If you found this repository helpful:

* ⭐ Star this repository
* 🍴 Fork it
* 📢 Share it with others

Happy Coding! 🚀
