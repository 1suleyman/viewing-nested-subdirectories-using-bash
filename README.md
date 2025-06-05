# 📁 Bash Script: Print Directory Structure (`tree.sh`)

## 🧾 Overview

This Bash script replicates a simplified version of the `tree` command. It prints the **directory structure** of a specified parent folder in a tree-like format — showing only **folders**, not files.

It’s especially useful when you want to:
- Visually explore nested directories
- Quickly see the folder hierarchy
- Learn or practice Bash scripting with real-world file operations

---

## 🛠️ Features

✅ Accepts an optional input argument (target directory)  
✅ Uses built-in shell commands to:
- Change directory (`cd`)
- Print working directory (`pwd`)
- Check for subfolders (`ls`, `grep`, `wc`)
- Format output (`sed`)  
✅ Prints message if no subdirectories are found  
✅ Recursively prints only the directory structure

---

## 📂 Example Output

```bash
/home/user/projects
 ├── Bash
 ├── Python
 └── Web
     ├── HTML
     └── CSS
````

---

## 🚀 How to Use

### 1. Make it executable:

```bash
chmod +x tree.sh
```

### 2. Run it from the terminal:

* For current directory:

```bash
./tree.sh
```

* For a specific directory (e.g. home folder):

```bash
./tree.sh ~
```

---

## 📄 How It Works

### Step-by-step logic inside the script:

1. **Check if argument is provided:**

   * If yes: `cd` into that directory
   * If not: stay in current directory

2. **Print current directory path:**

   * Uses `pwd`

3. **Check if there are any subdirectories:**

   ```bash
   ls -F -1 | grep "/" | wc -l
   ```

   * If none: print `-> no sub-directories`
   * If yes: continue

4. **Print full directory structure (recursive):**

   * Uses `ls -R` and pipes with `sed` to format output into tree shape

---

## 🧠 Commands Used

| Command | Purpose                                              |
| ------- | ---------------------------------------------------- |
| `cd`    | Change directory                                     |
| `pwd`   | Print current directory                              |
| `ls`    | List files and folders                               |
| `grep`  | Filter only directories (those with `/`)             |
| `sed`   | Format output into a tree structure                  |
| `wc -l` | Count number of lines (used to count subdirectories) |
| `echo`  | Print messages to the terminal                       |

---

## 🗂️ Files

* `tree.sh`: Main script file

---

## 💡 Tip

To make this script available anywhere, move it to your `~/bin/` folder (if available), and make sure that directory is in your `$PATH`.

```bash
mv tree.sh ~/bin/
```

