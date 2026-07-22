# ✏️ Editing Files in Linux

## 📖 Overview

In this lab, I learned how to create and edit files using two popular Linux command-line text editors: **Vim** and **Nano**.

I began by connecting to an Amazon Linux EC2 instance using SSH. I then used the `vimtutor` program to learn the basic functionality of Vim before creating and editing my own files.

I also practiced using Nano as an alternative text editor and learned how to create, save, edit, and exit files from the Linux command line.

---

## 🎯 Objectives

By completing this lab, I was able to:

- Use the `vimtutor` executable to learn the basics of Vim.
- Navigate and edit files using Vim.
- Create and save a file using Vim.
- Use Vim insert mode.
- Save and exit Vim.
- Delete lines and undo changes in Vim.
- Create and edit files using Nano.
- Save and exit Nano.

---

## 🛠️ Tools and Technologies Used

- Amazon EC2
- Amazon Linux
- SSH
- PuTTY
- Linux Bash Shell
- Vim
- `vimtutor`
- Nano

---

# Task 1 – Connecting to an Amazon Linux EC2 Instance

I began the lab by connecting to an Amazon Linux EC2 instance using SSH.

I used PuTTY to establish the connection and accessed the Linux command-line interface.

This provided the environment I needed to practice using Linux text editors.

---

# Task 2 – Learning Vim Using Vimtutor

I began by launching the Vim tutorial using:

```bash
vimtutor
```

The `vimtutor` program provided an interactive tutorial that introduced me to the basic functionality of the Vim text editor.

I worked through the initial Vim lessons and practiced concepts such as:

- Moving around a document.
- Navigating through text.
- Entering insert mode.
- Editing text.
- Saving files.
- Exiting Vim.

![Vim Tutorial](images/vimtutor.jpg)

After completing the tutorial exercises, I exited Vim using:

```vim
:q!
```

This allowed me to leave the editor without saving changes.

---

# Task 3 – Creating and Editing a File Using Vim

I then used Vim to create a new file called `helloworld`:

```bash
vim helloworld
```

This opened a new file in the Vim editor.

To begin entering text, I pressed:

```text
i
```

This placed Vim into **Insert Mode**.

I then added the following text:

```text
Hello World!
This is my first file in Linux and I am editing it in Vim!
```

![Creating a File Using Vim](images/vimhello.jpg)

Once I had finished entering the text, I pressed:

```text
ESC
```

This exited Insert Mode.

I then saved the file and exited Vim using:

```vim
:wq
```

The `:wq` command allowed me to:

- Save the changes.
- Quit the Vim editor.

---

## Editing the File Again

I reopened the file using:

```bash
vim helloworld
```

I then added another line:

```text
I learned how to create a file, edit and save them too!
```

![Editing a File in Vim](images/vimSecondLine.jpg)

After editing the file, I exited Vim without saving the changes using:

```vim
:q!
```

This helped me understand the difference between saving changes and exiting without saving.

---

## Additional Vim Commands

I also explored additional Vim commands:

### Delete a Line

```vim
dd
```

This deletes the current line.

### Undo the Last Command

```vim
u
```

This undoes the most recent change.

### Save Without Exiting

```vim
:w
```

This saves the current changes while keeping Vim open.

---

# Task 4 – Creating and Editing a File Using Nano

I then explored Nano, another command-line text editor.

I created a new file using:

```bash
nano cloudworld
```

This opened a new file called `cloudworld` in the Nano editor.

![Creating a File Using Nano](images/nano.jpg)

Unlike Vim, Nano does not require me to enter a separate Insert Mode before typing.

I was able to immediately enter the following text:

```text
We are using nano this time! We can simply start typing! No insert mode needed.
```

---

## Saving the File in Nano

To save the file, I used:

```text
CTRL + O
```

I then pressed Enter to confirm the file name.

To exit Nano, I used:

```text
CTRL + X
```

I then reopened the file using:

```bash
nano cloudworld
```

This allowed me to confirm that my changes had been successfully saved.

![Saving and Exiting Nano](images/nanoEnd.jpg)

---

# 💡 Key Concepts Learned

Through this lab, I learned how to:

- Use Vim within a Linux terminal.
- Use the `vimtutor` program.
- Create files using Vim.
- Enter Vim Insert Mode.
- Edit text in Vim.
- Save changes using `:w`.
- Save and exit using `:wq`.
- Exit without saving using `:q!`.
- Delete lines using `dd`.
- Undo changes using `u`.
- Create and edit files using Nano.
- Save files in Nano.
- Exit Nano using `CTRL + X`.

---

# 🧠 Skills Demonstrated

Throughout this lab, I developed practical experience with:

- Linux text editors
- Vim
- Vimtutor
- Nano
- File creation
- File editing
- Saving files
- Exiting command-line editors
- Linux command-line operations
- SSH remote access
- Amazon Linux

---

# 📚 Key Takeaways

This lab helped me understand how text files can be created and edited directly from the Linux command line.

I learned that Vim and Nano provide different approaches to editing files.

Vim uses different modes, including Insert Mode, and provides a wide range of keyboard commands for navigating and editing text.

Nano provides a simpler editing experience where I can immediately begin typing without entering a separate mode.

Understanding command-line text editors is an important Linux skill because they allow me to modify configuration files, create scripts, and edit files directly on remote servers.

These skills will be useful as I continue working with Linux-based systems and AWS cloud infrastructure.

---

## 🏁 Lab Completion

I successfully completed the **Editing Files** lab and strengthened my understanding of creating, editing, saving, and managing files using Vim and Nano within an Amazon Linux environment.
