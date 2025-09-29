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
