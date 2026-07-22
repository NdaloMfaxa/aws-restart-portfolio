# 🐧 Linux Command Line

## 📖 Overview

In this lab, I continued developing my Linux command-line skills by connecting to an Amazon Linux EC2 instance using SSH.

I practiced using common Linux commands to gather information about the current system, the active user session, system uptime, date and time information, and user and group details.

I also learned how to improve my workflow by using the Bash command history, reverse history searches, autocomplete, and shortcuts for rerunning previously used commands.

---

## 🎯 Objectives

By completing this lab, I was able to:

- Connect to an Amazon Linux EC2 instance using SSH.
- Run commands to gather information about the current system and session.
- Identify the current user.
- Display the hostname of the system.
- Check how long the system has been running.
- View information about logged-in users.
- Display dates and times for different time zones.
- Explore different calendar formats.
- View user ID and group information.
- Review previous Bash commands.
- Search through command history.
- Reuse previously entered commands.

---

## 🛠️ Tools and Technologies Used

- Amazon EC2
- Amazon Linux
- SSH
- PuTTY
- Linux Bash Shell
- Linux command-line utilities

---

# Task 1 – Connecting to an Amazon Linux EC2 Instance

I began the lab by connecting to an Amazon Linux EC2 instance using SSH.

Because I was working from a Windows computer, I used PuTTY as my SSH client.

After configuring the SSH connection, I successfully accessed the Amazon Linux command-line interface and was able to run commands directly on the remote EC2 instance.

This provided the environment I needed to practice Linux commands and explore the system.

---

# Task 2 – Running Familiar Linux Commands

I used several Linux commands to gather information about the system and my current session.

## Identifying the Current User

I used the following command:

```bash
whoami
```

This displayed the username of the user currently logged into the system.

The command returned:

```text
ec2-user
```

I also practiced using the Tab key for command autocomplete. For example, I entered part of the `whoami` command and used Tab to allow the shell to complete the command.

---

## Checking the Hostname

I used:

```bash
hostname -s
```

This displayed the shortened hostname of the computer I was connected to.

This command can be useful when identifying a particular system while troubleshooting or working with multiple servers.

---

## Checking System Uptime

I used:

```bash
uptime -p
```

This displayed how long the Linux system had been running in an easy-to-read format.

System uptime can be useful when troubleshooting and understanding how long a server has been active.

---

## Viewing Logged-In Users

I used:

```bash
who -H -a
```

This displayed information about users currently logged into the system.

The output included information such as:

- User name
- Terminal line
- Login time
- Idle time
- Process ID
- Comments
- Exit information

---

## Displaying the Date and Time in Different Time Zones

I used the following commands to display the current date and time for different locations:

```bash
TZ=America/New_York date
```

```bash
TZ=America/Los_Angeles date
```

These commands demonstrated how Linux can display time information for different time zones.

---

## Exploring Julian Dates

I used:

```bash
cal -j
```

This displayed the calendar using Julian dates.

This format represents days consecutively throughout the year rather than restarting the day count at the beginning of each month.

---

## Displaying Different Calendar Formats

I also used the following commands:

```bash
cal -s
```

and:

```bash
cal -m
```

These commands displayed alternative calendar layouts, allowing me to view the week starting on different days.

---

## Viewing User and Group Information

Finally, I used:

```bash
id ec2-user
```

This displayed information about the `ec2-user`, including the user's:

- User ID (UID)
- Group ID (GID)
- Group memberships

This helped me understand how Linux identifies users and manages group membership.

---

# Task 3 – Improving My Workflow Using Bash History

In the final task, I learned how to reuse previous commands instead of typing them again.

---

## Viewing Command History

I used:

```bash
history
```

This displayed a list of previously entered commands from the current Bash session.

This allowed me to review commands that I had already used during the lab.

---

## Searching Previous Commands

I used the keyboard shortcut:

```text
CTRL + R
```

This started a reverse history search.

I then searched for a previous command using:

```text
TZ
```

This allowed me to find an earlier command from my session and reuse or edit it.

I also practiced using Tab autocomplete and the arrow keys to modify commands before running them.

---

## Reusing the Previous Command

I first entered:

```bash
date
```

I then used:

```bash
!!
```

The `!!` command reran the most recently entered command.

This allowed me to execute the previous `date` command again without having to type it from scratch.

---

# 💡 Key Concepts Learned

Through this lab, I learned how to:

- Use Linux commands to gather system information.
- Identify the current logged-in user.
- Check the hostname of a system.
- Check system uptime.
- View information about logged-in users.
- Display time information for different time zones.
- Work with different calendar formats.
- View Linux user and group information.
- Review Bash command history.
- Search for previous commands.
- Use command autocomplete.
- Reuse previous commands efficiently.

---

# 🧠 Skills Demonstrated

Throughout this lab, I developed practical experience with:

- Linux command-line operations
- Amazon Linux
- SSH remote access
- Bash shell navigation
- System information commands
- User and group identification
- Date and time commands
- Command history
- Reverse history search
- Command reuse
- Terminal workflow efficiency

---

# 📚 Key Takeaways

This lab helped me become more comfortable working with the Linux command line.

I learned that the command line provides many useful tools for quickly gathering information about a system, its users, and its current state.

I also learned how Bash history and command shortcuts can improve efficiency. Features such as `history`, `CTRL + R`, Tab autocomplete, and `!!` make it easier to find and reuse commands without repeatedly typing them.

These skills will be useful as I continue working with Linux-based systems and cloud infrastructure within AWS.

---

## 🏁 Lab Completion

I successfully completed the Linux Command Line lab and strengthened my understanding of using Bash commands to explore system information and improve my command-line workflow.
