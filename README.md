# Basic knowlegde
**Handwritten Notes** are personal notes that I create in my own words while learning a concept.

**Documentation**, on the other hand, is the official and detailed explanation of a technology, usually provided by its creators or maintainers.

## What is Git and Github?
1. Git is a software (tool) used to track changes in code.
2. GitHub is an online service where we store and manage our Git projects.

***Git is a version control system (software) that helps developers track changes, manage code, and work with different versions.***

***GitHub is a cloud-based platform (hosting service) that allows us to store Git repositories online and collaborate with others.***

* Windows Terminal → general purpose terminal (cmd, PowerShell, etc.)
* Git Bash → terminal specially for Git + Linux commands
* VS Code Terminal
    * Opent terminal in vs code → ```ctrl+` ```
    * type: `bash` → open Git bash inside Vs code.
* Exit Git bash
    * press: `ctrl + d`
    * or type: `exit`


## Git learning
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

## Folder(repository) track or not track
1. Example: Create a random folder
* folder name: one, two, three, four
    * cmd: multiple repo create `mkdir one two three`
    * cmd: singel repo create `mkdir four`
2. if you want to track or not track
![image](https://docs.chaicode.com/_astro/repo-status.JIM1nCWI_Z205yrX.webp)
3. example: I want `one` folder to track by Git
    * `cd one`

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
        * how to exit press: q (quit)

## Creating a repository
Repository (repo) = a project folder tracker by Git

***Create Repository***

**`git init`** Convert normal folder → Git repository
* If repo already created (git init already done):

    * Running git init again is safe
    * It does NOT overwrite your project
    * It just reinitializes Git

1. 🔧 Steps to Create Repository
    * Create a folder
    * Example: my-project
2. Open terminal in that folder
3. Run command:
    * `git init`

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
![image](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*9nkjP2HhGYdJ4iqL1NzlZQ.png)
3. **📦 Staging Area (Repo Stage)**
 Staging area = place where files are prepared before commit

## Unstaging
Use git `rm --cached` to remove files from staging
- `git rm --cached file.txt` for one file
- OR `git rm --cached -r .` for all file
-  **`HEAD not found` No commit exists yet
Git cannot find HEAD (latest commit)**

## git commit(Repo)
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
