"""# 📁 Working with the File System

## 📖 Overview

In this lab, I combined my previous Linux knowledge to solidify and reinforce my capabilities by working with the Linux file system. I learned how to create folder structures, manage files, and reorganize directories using essential Linux commands.

I connected to an Amazon Linux EC2 instance using SSH and practiced creating directories, files, copying, moving, and deleting both files and folders from the command line.

---

## 🎯 Objectives

By completing this lab, I was able to:

- Create a folder structure from scratch.
- Create empty files using the `touch` command.
- Copy and move files and directories.
- Delete files and directories.
- Navigate the Linux file system using relative and absolute paths.
- Validate file system changes using `ls`, `pwd`, and `ls -laR`.

---

## 🛠️ Tools and Technologies Used

- Amazon EC2
- Amazon Linux
- SSH
- PuTTY
- Linux Bash Shell
- `mkdir`
- `touch`
- `cd`
- `ls`
- `pwd`
- `cp`
- `mv`
- `rm`
- `rmdir`

---

# Task 1 – Connecting to an Amazon Linux EC2 Instance

I began the lab by connecting to an Amazon Linux EC2 instance using SSH.

- **Windows Users:** Used PuTTY with the provided `.ppk` key file.
- **macOS/Linux Users:** Used the terminal with the provided `.pem` key file.

```bash
# macOS/Linux example
chmod 400 labsuser.pem
ssh -i labsuser.pem ec2-user@<public-ip>
```

This provided the environment I needed to practice Linux file system operations.

---

# Task 2 – Creating a Folder Structure

In this task, I recreated a specific folder structure for a fictional company, **CompanyA**.

## Target Structure

```
/home/ec2-user/CompanyA/
├── Finance/
│   ├── ProfitAndLossStatements.csv
│   └── Salary.csv
├── HR/
│   ├── Assessments.csv
│   └── TrialPeriod.csv
└── Management/
    ├── Managers.csv
    └── Schedule.csv
```

## Steps Taken

### Step 1: Create the Top-Level Directory

I verified I was in the home directory and created the main folder:

```bash
pwd
# Output: /home/ec2-user

mkdir CompanyA
cd CompanyA
```

### Step 2: Create Subdirectories

I created all three subdirectories at once:

```bash
mkdir Finance HR Management
ls
# Output: Finance HR Management
```

### Step 3: Create Files in the HR Folder

I navigated to the HR directory and created the required files:

```bash
cd HR
touch Assessments.csv TrialPeriod.csv
ls
# Output: Assessments.csv TrialPeriod.csv
```

### Step 4: Create Files in the Finance Folder

I moved to the Finance directory and created the files:

```bash
cd ../Finance
touch Salary.csv ProfitAndLossStatements.csv
ls
# Output: Salary.csv ProfitAndLossStatements.csv
```

### Step 5: Create Files in the Management Folder

I returned to the CompanyA folder and created files using a relative path:

```bash
cd ..
touch Management/Managers.csv Management/Schedule.csv
ls Management
# Output: Managers.csv Schedule.csv
```

### Step 6: Validate the Complete Structure

I used the recursive listing command to verify everything was created correctly:

```bash
ls -laR
```

**Output:**
```
.:
total 0
drwxr-xr-x 5 ec2-user root     49 Aug 10 13:36 .
drwx------ 4 ec2-user ec2-user 90 Aug 10 13:25 ..
drwxrwxr-x 2 ec2-user ec2-user 59 Aug 10 13:39 Finance
drwxrwxr-x 2 ec2-user ec2-user 52 Aug 10 13:37 HR
drwxrwxr-x 2 ec2-user ec2-user 46 Aug 10 13:39 Management

./Finance:
total 0
drwxrwxr-x 2 ec2-user ec2-user 59 Aug 10 13:39 .
drwxr-xr-x 5 ec2-user root     49 Aug 10 13:36 ..
-rw-rw-r-- 1 ec2-user ec2-user  0 Aug 10 13:39 ProfitAndLossStatements.csv
-rw-rw-r-- 1 ec2-user ec2-user  0 Aug 10 13:39 Salary.csv

./HR:
total 0
drwxrwxr-x 2 ec2-user ec2-user 52 Aug 10 13:37 .
drwxr-xr-x 5 ec2-user root     49 Aug 10 13:36 ..
-rw-rw-r-- 1 ec2-user ec2-user  0 Aug 10 13:37 Assessments.csv
-rw-rw-r-- 1 ec2-user ec2-user  0 Aug 10 13:37 TrialPeriod.csv

./Management:
total 0
drwxrwxr-x 2 ec2-user ec2-user 46 Aug 10 13:39 .
drwxr-xr-x 5 ec2-user root     49 Aug 10 13:36 ..
-rw-rw-r-- 1 ec2-user ec2-user  0 Aug 10 13:39 Managers.csv
-rw-rw-r-- 1 ec2-user ec2-user  0 Aug 10 13:39 Schedule.csv
```

> 💡 **Key Insight:** I learned that `touch` and `ls` can be used in two ways:
> - **Directly in the working folder:** `touch myFile.csv` creates the file in the current directory.
> - **Using a relative path:** `touch Management/myFile.csv` creates the file in a subdirectory.

---

# Task 3 – Deleting and Reorganizing Folders

A few weeks later, I was tasked with reorganizing the folder structure. The new structure required:

- Moving **Finance** and **Management** under **HR**
- Creating a new **Employees** folder under **HR**
- Moving **Assessments.csv** and **TrialPeriod.csv** into the **Employees** folder

## New Target Structure

```
/home/ec2-user/CompanyA/
└── HR/
    ├── Finance/
    │   ├── ProfitAndLossStatements.csv
    │   └── Salary.csv
    ├── Management/
    │   ├── Managers.csv
    │   └── Schedule.csv
    └── Employees/
        ├── Assessments.csv
        └── TrialPeriod.csv
```

## Steps Taken

### Step 1: Copy Finance Folder to HR

I copied the Finance folder and all its contents into the HR folder:

```bash
pwd
# Output: /home/ec2-user/CompanyA

cp -r Finance HR
ls HR/Finance
# Output: ProfitAndLossStatements.csv Salary.csv
```

### Step 2: Remove the Original Finance Folder

I first attempted to remove the Finance folder using `rmdir`:

```bash
rmdir Finance
# Output: rmdir: failed to remove 'Finance/': Directory not empty
```

> ⚠️ **Lesson Learned:** `rmdir` only works on **empty** directories.

I had two options:
1. Remove the files inside first, then remove the folder.
2. Use `rm -r` to recursively delete the folder and its contents.

I chose option 1 to practice both commands:

```bash
rm Finance/ProfitAndLossStatements.csv Finance/Salary.csv
ls Finance
# Output: (empty)

rmdir Finance
ls
# Output: HR Management
```

### Step 3: Move Management into HR

I moved the Management folder inside the HR folder:

```bash
mv Management HR
ls . HR/Management
# Output:
# .:
# HR
#
# HR/Management:
# Managers.csv  Schedule.csv
```

### Step 4: Create Employees Folder and Move HR Files

I navigated into the HR folder, created the Employees directory, and moved the HR files:

```bash
cd HR
mkdir Employees
mv Assessments.csv TrialPeriod.csv Employees
ls . Employees
# Output:
# .:
# Employees  Finance  Management
#
# Employees/:
# Assessments.csv  TrialPeriod.csv
```

---

# 💡 Key Concepts Learned

Through this lab, I learned how to:

- Create directories using `mkdir`.
- Create empty files using `touch`.
- Navigate directories using `cd` with absolute and relative paths.
- List directory contents using `ls` and `ls -laR`.
- Copy directories recursively using `cp -r`.
- Move files and directories using `mv`.
- Delete files using `rm`.
- Delete empty directories using `rmdir`.
- Understand the difference between `rmdir` (empty only) and `rm -r` (recursive).
- Validate file system changes at each step.

---

# 🧠 Skills Demonstrated

Throughout this lab, I developed practical experience with:

- Linux file system navigation
- Directory creation and management
- File creation and manipulation
- Copying and moving files and folders
- Deleting files and directories safely
- Using relative and absolute paths
- Validating file system state
- SSH remote access
- Amazon Linux command-line operations

---

# 📚 Key Takeaways

This lab helped me understand how to efficiently manage the Linux file system from the command line.

I learned that:

- **Planning the structure first** makes execution smoother.
- **Validating after each step** (`ls`, `pwd`) prevents errors from compounding.
- **`rmdir` vs. `rm -r`:** `rmdir` is safer for empty folders, while `rm -r` is more powerful but requires caution.
- **Relative paths** (`../`, `./`) save time when working deep in a directory tree.
- **The `touch` command** is a quick way to create empty files for testing or placeholder purposes.

These skills are foundational for managing servers, organizing project files, and automating file operations in Linux-based environments and AWS cloud infrastructure.

---

## 🏁 Lab Completion

I successfully completed the **Working with the File System** lab and strengthened my understanding of creating, organizing, copying, moving, and deleting files and directories within an Amazon Linux environment.
"""
