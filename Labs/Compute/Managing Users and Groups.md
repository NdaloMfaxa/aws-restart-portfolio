# 👥 Managing Users and Groups

## 📖 Overview

In this lab, I learned how to manage users and groups within an Amazon Linux environment.

I connected to an Amazon Linux EC2 instance using SSH and created multiple users with default passwords. I then created groups based on different departments and job roles and assigned users to the appropriate groups.

I also practiced switching between users and explored Linux permissions and the use of `sudo`. This allowed me to understand how different users have different levels of access within a Linux system.

---

## 🎯 Objectives

By completing this lab, I was able to:

- Create new Linux users.
- Assign default passwords to users.
- Create Linux groups.
- Add users to the appropriate groups.
- View user and group information.
- Switch between different users.
- Understand basic Linux file permissions.
- Understand the purpose of `sudo`.
- Identify what a sudoer is.
- View security logs related to unauthorized `sudo` attempts.

---

## 🛠️ Tools and Technologies Used

- Amazon EC2
- Amazon Linux
- SSH
- PuTTY
- Linux Bash Shell
- Linux users and groups
- `sudo`

---

# Task 1 – Connecting to an Amazon Linux EC2 Instance

I began the lab by connecting to an Amazon Linux EC2 instance using SSH.

I used PuTTY to establish the connection and accessed the Linux command-line interface as the `ec2-user`.

This provided the environment I needed to create users, manage groups, test permissions, and explore Linux access control.

---

# Task 2 – Creating Linux Users

I created multiple Linux users representing different employees and job roles within an organization.

The users included employees from departments such as:

- Sales
- Shipping
- Human Resources
- Finance
- Management
- Executive leadership

I used the following command to create a new user:

```bash
sudo useradd <UserID>
```

I then assigned a password to each user using:

```bash
sudo passwd <UserID>
```

I created users such as:

```text
arosalez
eowusu
jdoe
ljuan
mmajor
mjackson
nwolf
psantos
smartinez
ssarkar
```

I then verified that the users had been created by viewing the system's user database:

```bash
sudo cat /etc/passwd | cut -d: -f1
```

This allowed me to confirm that the new users were present on the system.

---

# Task 3 – Creating and Managing Groups

After creating the users, I created groups based on the different departments and roles within the organization.

The groups included:

```text
Sales
HR
Finance
Shipping
Managers
CEO
```

I created groups using:

```bash
sudo groupadd <Group>
```

For example:

```bash
sudo groupadd Sales
```

I then verified the groups by viewing the `/etc/group` file:

```bash
cat /etc/group
```

---

## Adding Users to Groups

I assigned users to the appropriate groups using the following command:

```bash
sudo usermod -a -G <Group Name> <User ID>
```

For example:

```bash
sudo usermod -a -G Sales arosalez
```

I assigned users to groups based on their departments and job roles.

Some users belonged to multiple groups. For example, managers were also members of the personnel-related groups.

I also added the `ec2-user` to the groups as part of the lab exercise.

I verified the group memberships using:

```bash
sudo cat /etc/group
```

This allowed me to confirm which users belonged to each group.

---

# Task 4 – Logging in as Different Users

After creating the users and assigning them to groups, I practiced switching between user accounts.

I used:

```bash
su arosalez
```

I then entered the user's password to switch to the `arosalez` account.

This allowed me to experience the Linux environment from the perspective of another user.

I used:

```bash
pwd
```

to check the current working directory.

---

# 🔐 Exploring Linux Permissions

While logged in as `arosalez`, I attempted to create a file in the `ec2-user` home directory using:

```bash
touch myFile.txt
```

The command failed with a permission denied message.

This demonstrated that the `arosalez` user did not have permission to write files in the `ec2-user` home directory.

This helped me understand that Linux users have different permissions depending on:

- The user account
- File ownership
- Group membership
- The permissions assigned to directories and files

---

# 🛡️ Understanding `sudo` and Sudoers

I then attempted to use:

```bash
sudo touch myFile.txt
```

However, the command was denied because `arosalez` was not included in the sudoers configuration.

This demonstrated that not every Linux user has permission to execute commands with elevated administrative privileges.

A user who is permitted to use `sudo` is known as a sudoer.

The lab showed that users who are not authorized to use `sudo` receive an error message indicating that they are not in the sudoers file.

This is an important security feature because administrative privileges should only be given to users who require them.

---

# 📋 Viewing Security Logs

After returning to the `ec2-user` account, I viewed the security log using:

```bash
sudo cat /var/log/secure
```

I was able to see that the unauthorized `sudo` attempt had been recorded in the security log.

This demonstrated how Linux records important security-related events, including attempts by users to perform unauthorized administrative actions.

---

# 💡 Key Concepts Learned

Through this lab, I learned how to:

- Create Linux users.
- Assign passwords to users.
- Create Linux groups.
- Assign users to groups.
- Manage users with different roles and responsibilities.
- Switch between user accounts.
- Understand basic Linux file permissions.
- Use the `su` command to switch users.
- Understand the purpose of `sudo`.
- Understand the role of sudoers.
- Identify unauthorized administrative actions.
- View security-related events in Linux logs.

---

# 🧠 Skills Demonstrated

Throughout this lab, I developed practical experience with:

- Linux user administration
- Linux group management
- User authentication
- Linux permissions
- User switching
- Administrative privileges
- `sudo`
- `su`
- Linux security logs
- Amazon Linux
- SSH remote access

---

# 📚 Key Takeaways

This lab helped me understand how Linux manages users, groups, permissions, and administrative access.

I learned that users can be organized into groups based on their roles and responsibilities. Group membership can then be used to manage access to resources more efficiently.

I also learned that not every user should have administrative privileges. The `sudo` system provides a way to control which users can perform commands that require elevated permissions.

The lab also demonstrated the importance of security logging. When a user attempts to perform an unauthorized administrative action, the event can be recorded in the system's security logs.

These concepts are important for managing and securing Linux systems in cloud environments.

---

## 🏁 Lab Completion

I successfully completed the Managing Users and Groups lab and strengthened my understanding of Linux user administration, group management, permissions, administrative privileges, and security logging.
