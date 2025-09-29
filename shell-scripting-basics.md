# Shell Scripting

## What is the Shell?

- Shell acts as a **command interpreter**.  
  It takes the commands entered by the user (CLI or GUI) and executes them by communicating with the **OS kernel**.

- The default shell is **BASH (Bourne Again SHell)**.

- Different shells available in the market:
  1. Korn Shell  
  2. BASH Shell  
  3. C Shell  
  4. Z Shell (zsh)  
  5. ksh  
  6. sh (old one)  

## How to check how many shells are present in Linux server?
```bash
cat /etc/shells
````

---

## How to install any other shell?

```bash
sudo yum install csh -y
```

---

## How to see which shell you are connected to at present?

### Method 1: Using environment variable

```bash
echo $SHELL
```

* **Note:** `$SHELL` is a system-defined variable.
* It shows only the **default shell**, not necessarily the current one.

### Method 2: Using process information

```bash
echo $0
```

```bash
ps -p $$
```


# How to Switch to Another Shell in Linux

## Step 1: Check which shells are present
```bash
cat /etc/shells
````

---

## Step 2: Check the current shell we are using

```bash
ps -p $$
```

---

## Step 3: Switch the shell

```bash
/bin/csh
```


# What is Shell Scripting?

- Shell Scripting is a file that contains a collection of commands.  
- Whatever the order you provide, commands will be executed **from top to bottom**.  

---

## What is the extension of Shell Scripting?

- `.sh` (optional)  
- As a good practice, use `.sh` to easily identify shell script files.  

---

## Why do I need to learn Shell Scripting?

- To automate **repetitive manual tasks**.  

---

## Is Shell Scripting only for DevOps?

- No, it can also be useful for:  
  - Java Developers  
  - Testers  
  - And many others  

---

## Examples of Shell Scripts

- `dbbackup.sh`  
- `serverresourceutilization.sh`  

---

# Prerequisites for Learning Shell Scripting

1. Linux Commands  
2. Java fundamentals / Basic programming fundamentals  


# How to Write a Shell Script

```bash
vi first.sh
````

Example content of `first.sh`:

```bash
echo "I am from nellore"
echo "How are you"
echo "Today date is:"
date
pwd
```

---

# How to Run a Shell Script

There are **4 approaches** to run a shell script:

1. `sh first.sh` → no need to give execute permissions
2. `./first.sh` → requires execute permission for user

   ```bash
   chmod u+x first.sh
   ```
3. `. first.sh`
4. `bash first.sh`

---

# Does Shell Scripting Work on Windows?

* ❌ **No**, shell scripting is for Linux/Unix-like environments.

---

# Platform Dependency

* **Linux** → Shell scripting
* **Windows Server** → PowerShell

---

# Python Platform Support

* ✅ **Python is platform-independent**
* Works on **Linux** and **Windows** servers.



# How to Run the Shell Script in Debug Mode

```bash
sh -x first.sh
````

---

# How to Run One Command in Debug Mode

* Open the shell script file and add debug points:

```bash
set -x   # starting point  
set +x   # ending point  
```

Example:

```bash
sh first.sh
```

* To run all commands in debug mode:

```bash
sh -x first.sh
```

---

# What is Shebang Line?

```bash
#!/bin/bash
```

* This line is **optional**, but as a **good practice** we should include it.

---

# Comments in Shell Scripting

* Used to **improve readability** of the script.
* Can be used to **stop execution** of one or more commands.

---

## Types of Comments

1. **Single-line comment**
2. **Inline comment**
3. **Multi-line comments**

---

### 1. Single-line Comment

* Begins with `#` (hash).
* Ignored by the shell.

Example:

```bash
# single line comment
```

---

### 2. Inline Comment

* Written in the middle of a line.

Example:

```bash
date # This is date command
```

---

### 3. Multi-line Comments

* Used when you want to comment multiple lines.

**Syntax:**

```bash
<<comment
--
--
--
comment
```

**Example (for documentation in real time):**

```bash
<<comment
Author: Gireesh
AIM: To run commands
Start: 28/09/2025
comment
```
