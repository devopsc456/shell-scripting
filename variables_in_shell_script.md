# Variables in Shell Scripting

Variable is the name of the memory location where we store values.  
The value can be changed during the program (script) execution.

---

## How to assign a value to a variable?

```sh
a=12
b=23
name="Gireesh"
````

# Rules for Declaring Variables in Shell Scripting

1. **Variable names can contain letters (a-z, A-Z), digits (0-9), and underscore (_)**
   - ✅ Example:  
     ```sh
     name=100
     ```
   - ❌ Example:  
     ```sh
     %6#a=90
     ```

2. **Variable names cannot start with a number**
   - ❌ Example:  
     ```sh
     23e=999
     ```

3. **Variable names must start with either an underscore (_) or a letter, but not a digit**
   - ✅ Example:  
     ```sh
     _abc=123
     ```
   - ❌ Example:  
     ```sh
     2a_=999
     ```

4. **Spaces are not allowed in variable names**
   - ❌ Example:  
     ```sh
     ad de=90
     ```

5. **Variable names are case-sensitive**
   - ✅ Example:  
     ```sh
     name=10
     Name=20
     ```
   - Here, `name` and `Name` are treated as different variables.


# How to Access a Variable?

To access a variable in shell scripting, use **`$`** followed by the variable name.

### Example:
```sh
echo $a
````

---

## Example Program

**File Name:** `variables.sh`

```sh
a=20
b=40
name="Gireesh"

echo "A Value is : $a"
echo "B Value is : $b"
echo "name is : $name"

a=89
echo "A value is : $a"   # Overrides the previous value and stores the latest value.

fname="kk"
sname="funda"
echo "full name is ------> $fname $sname"   # Concatenating the variables (or) strings.

age=31
name="Gireesh"
echo "$name age is $age"
```

# Types of Variables in Shell Scripting

There are **two types of variables** in shell scripting:

1. **System Defined Variables (Environmental Variables)**  
   - These variables are inherited from the shell environment.

---

## How to Check System Defined Variables in Linux?

```sh
env
printenv
````

To get the count of system variable names:

```sh
env | wc -l
```

---

## Example of a System Defined Variable: `HISTSIZE`

* `HISTSIZE` is a system-defined variable used to store the history size of commands.
* By default, the value of `HISTSIZE` is **1000**.

### How to Change `HISTSIZE`?

```sh
export HISTSIZE=799
```

---

## Example

```sh
echo $USER
echo $HISTSIZE
```

2. **Programmer / User Defined Variables**  
   - These are variables defined by the programmer or user.

---

## Example

```sh
age=31
name="Sai"
amount=2000
````

# Naming Conventions in Shell Scripting

1. **Shell file name**: Maximum limit is **255 characters**.  
2. **Avoid using system-defined commands** as shell file names.

---

## Syntax for Variable Declaration

```sh
VariableName=<Value>
````

---

## Example

```sh
a=40
name="sai"
```

# Command Line Arguments in Shell Scripting

## What is a Command Line Argument?
- While running a shell script, if you are passing any values, those are called **Command Line Arguments**.

### Example:
```sh
sh test.sh one 10 34 sai
````

---

## Accessing Command Line Arguments

* `echo $0` → File name of the script
* `echo $1` → First argument
* `echo $2` → Second argument
* `echo $3` → Third argument
* `echo $n` → n-th argument

⚠️ In shell scripting, `$` followed by a single digit is considered as one argument.
It will not directly work with **double-digit arguments**.

---

### Example 1

**File:** `commandline.sh`

```sh
echo $0
echo $12
echo $2
```

**Run:**

```sh
sh commandline.sh one
```

**Output:**

```
commandline.sh
one2
```

---

## Accessing Arguments Beyond 9

To access the 11th (or higher) command line argument, use **`${}`** syntax:

```sh
echo ${11}
```

---

### Example 2

**File:** `commandline.sh`

```sh
echo $0
echo ${12}
echo $2
```

**Run:**

```sh
sh commandline.sh one 2 3 4 5 6 7 8 9 10 11 12 13
```

**Output:**

```
commandline.sh
12
2
```

# Special Variables in Shell Scripting

1. **`$#`** → Displays the **total number of arguments** passed through the script.  
2. **`$@`** → Displays all values as separate strings (treats each as an individual argument).  
   - Example: `"one" "sai" "kk" "funda"`  
3. **`$*`** → Displays all values as a single string.  
   - Example: `"one sai kk funda"`  
4. **`$$`** → Displays the **process ID (PID)** of the currently running script.  
5. **`$?`** → Displays the **exit status of the previous command**:  
   - `0` → Success  
   - `127` → Failure  

---

## Example Program

**File:** `specialvariables.sh`

```sh
echo $1
echo "welcome to KK FUNDA"
echo $2
echo $4
echo "status code for previous command $? "
echo $3
echo $#
echo $@
echo $*
echo $$
````


