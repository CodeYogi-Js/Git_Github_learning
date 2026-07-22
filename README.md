# Basic knowlegde
**Handwritten Notes** are personal notes that 
I create in my own words while learning a concept.

**Documentation**, on the other hand, is the official
and detailed explanation of a technology, usually
provided by its creators or maintainers.

## What is Git and Github?
1. Git is a software (tool) used to track changes in code.
2. GitHub is an online service where we store and manage our Git projects.

***Git is a version control system (software) that helps developers track changes, manage code, and work with different versions.***

***GitHub is a cloud-based platform (hosting service) that allows us to store Git repositories online and collaborate with others.***

## Windows Terminal, Git Bash, VScode Terminal.
* Windows Terminal → general purpose terminal (cmd, PowerShell, etc.)
* Git Bash → terminal specially for Git + Linux commands
* VS Code Terminal
    * Opent terminal in vs code → ```ctrl+` ```
    * type: `bash` → open Git bash inside Vs code.
* Exit Git bash
    * press: `ctrl + d`
    * or type: `exit`

## Create Folder(repository) Convert Git Repo (track or not track)
1. Example: Create a random folder
* folder name: one, two, three, four
    * cmd: multiple repo create `mkdir one two three`
    * cmd: singel repo create `mkdir four`
2. if you want to track or not track
![image](https://docs.chaicode.com/_astro/repo-status.JIM1nCWI_Z205yrX.webp)
3. example: I want `one` folder to track by Git
    * `cd one`

## Start Learning Git
1. Step 1: `install Git`
    - download from official website [Git](https://git-scm.com/)
    - Install in system.
2. Step 2: check Git installed or not
    - Command: `git --version`
    - if version shows → Git working.
3. Step 3: Open project Folder
    - go to any folder(repository)
4. Step 4: Check Git status
    - Command: `git status`
        - Error: `fatal: not a git repository (or any of the parent directories): .git`
            - Meaning: Current folder is not a Git repository
            - Reason: .git folder not found
        - Happens when:
            - In wrong directory
            - Git not initialized
        - Fix:
            - Go to correct project folder
            - OR run `git init`

## Git Config
 **Git config** is used to set and manage settings in Git. Set your name and email , Control how git works.

 **Git** has two main config types.

1. 🌍 Global Config
    * Applies to all repositories
    * Set once in your system

    * 👉 Example:

        * `git config --global user.name "Your Name"`
        * `git config --global user.email "your@email.com"`
2. 📁 Local (Directory) Config
    * Applies to only one project (repository)
    * Stored inside that folder
    * 👉 Example:
        * `git config user.name "Project Name"`
        * `git config user.email "project@email.com"`
        * `git config --list shows all Git settings.`
        * how to exit press: **`q (quit)`**

## If Again Git Repo Create?
Repository (repo) = a project folder tracker by Git

***Create Repository***

**`git init`** Convert normal folder → Git repository
* If repo already created (git init already done):

    * Running git init again is safe
    * It does NOT overwrite your project
    * It just reinitializes Git
    * insted of `git init` check `git status`

## Complete get flow
Git flow = the steps/process of using Git to manage code
![image](https://docs.chaicode.com/_astro/complete-flow.DYr-Pvsp_1IQISm.webp)

## git add
`git add` is used in Git to add files to staging area.
- Prepares files before commit
- Moves files → staging area
**Example**
- `git add file1.txt file2.txt`→ add one file
- `git add .` → add all files
1. After git add → files go to staging area
2. Run git status → shows file is ready to commit

```Bash
Terminal

$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        file1.txt
        file2.txt

nothing added to commit but untracked files present (use "git add" to track)
```
3. **📦 Staging Area (Repo Stage)**
 Staging area = place where files are prepared before commit

## ⭐Unstaging
Use git `rm --cached` to remove files from staging
- `git rm --cached file.txt` for one file
- OR `git rm --cached -r .` for all file
- ⭐⭐⭐`git rm --cached = untrack file (keep locally)`
-  **`HEAD not found` No commit exists yet
Git cannot find HEAD (latest commit)**
- git restore --staged file
Unstage file (undo git add)

## Git commit(Repo)
git commit = save changes permanently
Creates a snapshot (version) of your code
* Example:
    1. `git commit -m "first commit"`
* 📌 Meaning:
    2. Your work is now saved in Git history
    3. show: ***nothing to commit, working tree clean***
    4. after commit some add content in file.txt need staging means `git add file.txt` and then repo stage do `git commit -m "add new content"`

## Check History Of Commit
`git log` is a Git command that shows the history of commits in your repository. It lists commits in reverse chronological order (most recent first).Each commit usually shows:

* Commit hash: A unique ID for the commit (long string like 3f5a1e7).
* Author: Who made the commit.
* Date: When the commit was made.
* Commit message: The description you wrote when committing.

```Bash
Terminal 

commit 3f5a1e7b2c3d4e5f67890123456789abcdef1234
Author: Babu Das <babu@example.com>
Date:   Fri Apr 5 11:20:15 2026 +0530

    Added README file with project description

commit 2a4b6c8d9e0f1a2b3c4d5e6f7a8b9c0d1e2f3a4b
Author: Babu Das <babu@example.com>
Date:   Thu Apr 4 18:45:10 2026 +0530

    Initial commit
```
**Show a one-line summary (easy to read):**
`git log --oneline`

**Show commit messages for a specific file:**
`git log -- file1.txt`

## Repo Modify || Add Content File
*`git add` and `git commit -m 'add msg'` need every time to same.*

## Only `git commit` How to solve 
If you just type `git commit,`Git opens the default text editor (usually Vim or Nano) for the commit message.
1. Press `i` → type your commit message.
2. Press `Esc` → back to Normal mode.
3. `delete` key → the character under the cursor
    - **How to save**
    - Press `Esc` — to make sure you’re in Normal mode.
    - Type :wq — this stands for write and quit.
    - Press Enter — this saves your commit message and exits Vim, completing the commit.
    - *`:q!` → exit without saving (if you want to abort the commit)*

## Common File .env and Gitignore
1. What is .env?

    env is a file to store environment variables like API keys, DB passwords, or secret tokens.

```Bash
Example 

DB_HOST=localhost
DB_USER=admin
DB_PASS=supersecret
API_KEY=123456
```
 
When check `git status` so the result


```Bash
Terminal

On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .env

nothing added to commit but untracked files present (use "git add" to track)  
```
Git tracking this `.env` file so stop to use `.gitignore`

2. What is `.gitignore` file?
    
    `.gitignore` is a text file that tells Git which files or folders to ignore. Git will not track or commit them.
        
     Useful for: sensitive files, build files, OS-generated files, or node_modules in Node.js projects.

```Bash
Example:

node.js dependencies
node_modules/

dist/
build/

#Environment variables
.env
```
**If you add `.gitignore` file inside `.env` after git tack only `.gitignore`**

```Bash
Terminal:

$ git status
On branch master
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore

nothing added to commit but untracked files present (use "git add" to track)     
```
*Now you can only tack `.gitignore` file.*


## *Tack Empty folder `.gitkeep`*
Git doesn’t track empty folders,Git tracks files, not folders. If a folder has no files, Git ignores it

1. If you have a project inside an empty folder and want Git to track it, create a placeholder file (commonly `.gitkeep`) inside the empty folder. Then Git will track the folder because it now contains a file.
```Bash
Example

mkdir myfolder
touch myfolder/.gitkeep
git add myfolder/.gitkeep
git commit -m "Track empty folder myfolder"
```

## Branches in Git
A Git branch is a separate line of development that allows you to work on changes without affecting the main project.

![branch](https://docs.chaicode.com/_astro/branches.YOIsOP4X_Z2gjmSk.webp)

*master* was the default branch name in older versions of Git. Newer versions use *main* as the default for better and more inclusive naming. <u>Both are just branch names and work the same way.</u>

**HEAD** in Git is a reference (pointer) that points to the current branch or the latest commit you are working on. It represents your current position in the repository.

## Branch Command
1️⃣ `git branch` = “show or manage different versions (lines) of your project”

2️⃣ `git branch bug-fix` = “Creates a new branch, but does not switch to it”

3️⃣ `git switch bug-fix` = "Go to the bug-fix branch and start working there"

4️⃣ If `bug-fix` branch already exists → you will switch to it.
Your working files now reflect that branch

**❌ If branch does NOT exist**
```Bash
Terminal

fatal: invalid reference: bug
```
5️⃣ `git switch -c dark-mode`
= "Create a new branch 'dark-mode' and go there"

6️⃣ `git checkout orange-mode`
= "Go to the orange-mode branch"
7️⃣ `git branch -m old-name new-name` = change branch name

8️⃣ `git branch -d branch-name` = "delete that branch (safe)"


If orange-mode branch already exists → you move to it
Your files change to match that branch

*❌ If branch does NOT exist*
```Bash
Terminal

error: pathspec 'orange-mode' did not match any file(s) known to git
```

## Merging Branches
Merging means: combining changes from one branch into another branch
- ⭐How to merge (step by step)
    - main (original code)
    - dark mode (new feature)

1. 1️⃣Go to the branch you want to merge INTO
    - `git switch main` (I want changes in main)
    - now dark-mode changes added into main

2. 2️⃣ Merge the other branch
    - `git merge dark-mode`

```Bash 
Before

main:        A --- B --- C
                    \
dark-mode:            D --- E

After
main:        A --- B --- C ------- M
                    \           /
dark-mode:            D --- E
```

***⚠️ Merge Conflict (important)***
Sometimes Git cannot merge automatically. Same file edited in both branches. You’ll get conflict.

```Bash
⭐⭐⭐Fix confilt:
1️⃣Open the file
2️⃣ you'll see:
<<<<<<< HEAD
main code
 =======
dark-mode code
>>>>>>> dark-mode
3️⃣Edit manually (choose correct code)
4️⃣Then:
git add .
git commit
```

## Git Diff, Stash and Tag

## Git Rebase and reflog