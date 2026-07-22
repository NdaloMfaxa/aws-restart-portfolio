# 🐧 Introduction to an Amazon Linux AMI

## 📖 Overview

In this lab, I reinforced my understanding of the Linux command-line interface by connecting to an Amazon Linux Amazon Machine Image (AMI) hosted on an Amazon EC2 instance.

I used Secure Shell (SSH) to connect to the Linux instance from my Windows computer using PuTTY. After establishing the connection, I explored the Linux manual pages using the `man` command.

This lab helped me become more familiar with accessing a Linux server remotely and using built-in Linux documentation to learn about commands and their available options.

---

## 🎯 Objectives

By completing this lab, I was able to:

- Use SSH to access an Amazon Linux AMI.
- Connect to an Amazon EC2 instance using PuTTY.
- Understand the purpose of the Linux `man` command.
- Explore Linux manual pages.
- Identify the main sections of a manual page.
- Use the search and navigation features within the `man` pages.
- Exit the manual page interface using the `q` command.

---

## 🛠️ AWS Services and Tools Used

- Amazon EC2
- Amazon Linux AMI
- Secure Shell (SSH)
- PuTTY
- Linux Bash Shell
- Linux `man` command

---

# Task 1 – Connecting to an Amazon Linux EC2 Instance Using SSH

I began the lab by connecting to an Amazon Linux EC2 instance using SSH.

Because I was working from a Windows computer, I used **PuTTY** as my SSH client.

I first configured PuTTY by entering the public IP address of the EC2 instance and using port `22`, which is the default port for SSH connections.

### PuTTY Configuration

The connection was configured using:

| Setting | Configuration |
|---------|---------------|
| Host Name | Public IP address of the EC2 instance |
| Port | 22 |
| Connection Type | SSH |

I then configured the required private key for authentication and opened the SSH session.

After successfully connecting to the instance, I was presented with the Amazon Linux command-line interface.

The terminal confirmed that I was logged in as the `ec2-user`.

```text
ec2-user@ip-10-0-10-22
```

This demonstrated that I had successfully established an SSH connection to the remote Amazon Linux EC2 instance.

---

# Task 2 – Exploring the Linux `man` Pages

After connecting to the Amazon Linux instance, I explored the Linux manual pages.

The Linux `man` command provides access to the system's built-in documentation for commands, utilities, and system functions.

I opened the manual page for the `man` command itself by entering:

```bash
man man
```

This opened the manual page for the `man` utility.

---

## Exploring the Manual Page Sections

While viewing the manual page, I explored the different sections used to organize information about Linux commands.

Some of the important sections I identified included:

- `NAME`
- `SYNOPSIS`
- `DESCRIPTION`
- `OVERVIEW`
- `EXAMPLES`
- `FILES`
- `OPTIONS`
- `SEE ALSO`

These sections provide different types of information about a command.

For example:

### NAME

Provides the name of the command and a brief description.

### SYNOPSIS

Shows the general syntax and available structure for using the command.

### DESCRIPTION

Provides a more detailed explanation of what the command does and how it works.

### OPTIONS

Displays the different options and arguments that can be used with the command.

### SEE ALSO

Provides references to related manual pages and commands.

---

## Navigating the `man` Pages

I used the arrow keys to move through the manual page and examine the available information.

The `man` command uses a pager to display information that is longer than the terminal window.

After exploring the manual page, I exited the interface by pressing:

```text
q
```

This returned me to the normal Linux command prompt.

---

# 💡 Key Concepts Learned

Through this lab, I learned that:

- SSH provides a secure way to connect to remote Linux servers.
- Amazon EC2 instances can be accessed through a command-line interface.
- PuTTY can be used as an SSH client on Windows.
- The Linux `man` command provides built-in documentation.
- Manual pages are divided into organized sections.
- The `man` command is useful when learning unfamiliar Linux commands.
- Linux commands can often be explored directly from the terminal without requiring external documentation.

---

# 🧠 Skills Demonstrated

Throughout this lab, I demonstrated the following skills:

- Connecting to a remote Linux server using SSH
- Using PuTTY to access an Amazon EC2 instance
- Navigating a Linux terminal
- Using the Linux `man` command
- Reading Linux command documentation
- Understanding command syntax and options
- Navigating terminal-based documentation

---

# 📚 Key Takeaways

This lab strengthened my understanding of working with Linux-based cloud servers.

I learned how to use SSH to remotely connect to an Amazon Linux EC2 instance and how to use the Linux `man` command to access documentation directly from the command line.

One of the most important lessons I took from this lab is that Linux provides extensive built-in documentation. Instead of having to memorize every command and option, I can use the `man` command to research how a command works and understand the available options.

This will be especially useful as I continue working with AWS services and Linux-based cloud infrastructure.

---

# 📸 Evidence of Completed Lab

The lab included practical evidence of my work, including:

- PuTTY SSH configuration
- Successful connection to the Amazon Linux EC2 instance
- The `man man` command being executed
- Navigation through the Linux manual pages
- Exiting the manual pages using the `q` command

---

## 📁 Repository Structure

```text
aws-linux-ami-introduction/
│
├── README.md
│
└── images/
    ├── putty-configuration.png
    ├── ssh-connection.png
    ├── man-command.png
    └── exit-man-pages.png
```

---

## 🏁 Lab Completion

I successfully completed the lab by connecting to an Amazon Linux EC2 instance using SSH and exploring the Linux manual pages with the `man` command.

This lab provided me with a foundation for continuing to work with Linux command-line tools and Amazon Linux environments in AWS.
