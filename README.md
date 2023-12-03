## Notes for Git
I am tring to collect note for a wonderful course for git 
*McCullough and Berglund on Mastering Git*

## 1. Set up git and configure git

### 1.1 Install Git:
- If Git is not already installed on your system, you can download and install it from the official website: [Git Downloads](https://git-scm.com/downloads).

### 1.2 Configure Git with Your Identity:
- Open a terminal (Command Prompt on Windows, Terminal on macOS/Linux) and set your name and email address. This information will be used to identify your commits.
```bash
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
```
### 1.3 Set Up Default Text Editor:
 - Git uses a text editor for commit messages. If you haven't set one, Git will use the system default. You can set it using:
  ```bash
  git config --global core.editor "your-preferred-editor"
  ```
Replace "your-preferred-editor" with the text editor you want to use (e.g., "nano," "vim," "code" for Visual Studio Code).

### 1.4 Checking Configuration:
To verify your configuration, you can use:
```bash
git config --list
```
### 1.5 Initialize a Repository 
```
git init
```
### 1.6 Check Git status:
To see the status of your changes:
```bash
git status
```

## 2. Three stage of git file work flow
The three stages of the Git file workflow, often referred to as the "three-tree architecture," are the Working Directory, the Staging Area (Index), and the Repository. Here's how you switch between them using Git commands:
- Working Directory to staging Area: 
```bash
git add <file1>
```
> Use git add to move changes from the Working Directory to the Staging Area. This command stages specific files for the next commit. You can also use git add . to stage all changes.
- Staging Area to Repository:
```bash
git commit -m "Your commit message"
```
> The git commit command takes the changes in the Staging Area and permanently saves them in the Git repository. The -m flag allows you to add a commit message directly from the command line.

- Repository to working Directory:
```bash
git checkout <commit-hash> <file1> <file2> ...

```
> Use git checkout to revert changes in the Working Directory to a specific commit from the Git repository. This command can be used to discard changes and bring your Working Directory in sync with a previous commit.
- Switching Between Branches:
If you are working with branches, you can switch between branches using:
```bash
git checkout <branch-name>
```
- Creating a Branch:
To create and switch to a new branch simultaneously, you can use:
```bash
git checkout -b <new-branch-name>
```

## 3. Cloning
Cloning in Git refers to the process of creating a copy of a remote repository on your local machine. This allows you to work on the code, track changes, and contribute to the project. Here are the steps to clone a Git repository:

1. Get the Repository URL:
   - You need the URL of the Git repository you want to clone. This URL is usually provided by the hosting service (e.g., GitHub, GitLab).

2. Open Terminal or Command Prompt:
   - Open your terminal or command prompt on your local machine.

3. Navigate to the Directory Where You Want to Clone:
   - Use the `cd` command to navigate to the directory where you want to store the cloned repository.

   ```bash
   cd path/to/your/directory
   ```

4. Clone the Repository:
   - Use the `git clone` command followed by the repository URL.

   ```bash
   git clone repository-url
   ```

   Replace `repository-url` with the actual URL of the Git repository.

   Example:
   ```bash
   git clone https://github.com/example/repository.git
   ```

5. Navigate into the Cloned Repository:
   - After cloning, use the `cd` command to enter the cloned repository directory.

   ```bash
   cd repository
   ```

   Replace `repository` with the actual name of the cloned repository.

Now, you have successfully cloned a Git repository onto your local machine. The cloned repository contains all the project files and the complete Git history.

### Additional Notes:

- Cloning a Specific Branch:
  If you want to clone a specific branch, you can specify it after the repository URL.

  ```bash
  git clone -b branch-name repository-url
  ```

  Replace `branch-name` with the name of the branch you want to clone.

- Cloning into a Specific Directory:
  If you want to clone into a directory with a name different from the repository name, you can specify it after the repository URL.

  ```bash
  git clone repository-url target-directory
  ```

  Replace `target-directory` with the name of the directory you want.

Now you're ready to work with the cloned repository, make changes, and contribute to the project.
## 4. Storage and hashs

Git uses a unique identifier called a "hash" or "commit hash" to represent different versions of a project. Each commit in Git is identified by a SHA-1 hash, a 40-character hexadecimal number, which is essentially a unique fingerprint for that specific commit. This hash is generated based on the content of the commit, including the changes made, the commit message, and metadata like the author and timestamp.

Here's a clarification of how Git deals with versions and changes using commit hashes:

### 4.1 Committing Changes:
   - When you make changes to your project and are ready to save those changes, you create a new commit using the `git commit` command.
   - Git generates a unique hash for the commit based on the content of the changes.

   ```bash
   git commit -m "Your commit message"
   ```

### 4.2 Commit Hashes:
   - Each commit has a unique 40-character hash that represents the state of the project at that particular point in time.
   - This hash is used to reference and identify the commit in the Git history.

### 4.3 Viewing Git History:
   - You can view the history of commits using the `git log` command, which shows the commit hashes, commit messages, authors, and timestamps.

   ```bash
   git log
   ```

### 4.4 Referencing Commits:
   - Git allows you to reference commits using their full hash or a shorter unique prefix of the hash (typically the first 7 characters).

   ```bash
   git show abc1234  # where abc1234 is the first 7 characters of the commit hash
   ```

## 5. Branches
In Git, a branch is a lightweight, movable pointer to a specific commit in the version history of a Git repository. Think of a branch as a line of development that diverges from the main line (usually called the "master" branch) to work on different features, bug fixes, or experiments. Branches allow multiple lines of development to coexist in parallel, and they make it easier to isolate changes and manage collaborative development.

Key points about branches in Git:

### 5.1 Master Branch:
   - The default and often primary branch in a Git repository is commonly named "master." However, some projects use alternative names such as "main."
   - The master branch usually represents the stable, production-ready version of the project.

### 5.2 Creating a New Branch:
   - You can create a new branch using the `git branch` command. For example:

     ```bash
     git branch new-feature
     ```

   - This command creates a new branch named "new-feature" but does not switch to it yet.

### 5.3 Switching Between Branches:
   - You can switch to a different branch using the `git checkout` command or, in Git version 2.23 and later, the `git switch` command.

     ```bash
     git checkout new-feature
     ```

     or

     ```bash
     git switch new-feature
     ```

   - Alternatively, you can create and switch to a new branch in one command using:

     ```bash
     git checkout -b new-feature
     ```

     or

     ```bash
     git switch -c new-feature
     ```

### 5.4 Viewing Branches:
   - To see a list of branches and identify the currently active branch, you can use:

     ```bash
     git branch
     ```

   - The active branch is usually indicated with an asterisk (`*`).

### 5.5 Merging Branches:
   - Once you've made changes on a branch and want to incorporate those changes back into the master branch, you perform a branch merge.

     ```bash
     git checkout master
     git merge new-feature
     ```

   - This combines the changes from the "new-feature" branch into the "master" branch.

### 5.6 Branch Naming Conventions:
   - It's common to use meaningful names for branches, such as "feature/add-login-page" or "bugfix/fix-broken-link."
   - Some projects adopt specific naming conventions to help organize and categorize branches.

### 5.7 Branching Strategies:
   - Git branching strategies, like Git Flow or GitHub Flow, provide guidelines on how to manage branches in a project. These strategies define when and how branches should be created, merged, and released.


## 6. remote
- You can have as many as remote repos that you want
- The default name is *origin*
  > it does not have any special thing  it is just a default name and also can be renamed
- you can add remote and check your remote as below
```bash
ayman@ubuntu-tst:~$ git remote add origin https://github.com/AymanMoElhussiny/hello-remote.git
ayman@ubuntu-tst:~$ git remote -v
origin  https://github.com/AymanMoElhussiny/hello-remote.git (fetch)
origin  https://github.com/AymanMoElhussiny/hello-remote.git (push)
```
- you can add any name you want for example *another*
```
ayman@ubuntu-tst:~$ git remote add another https://github.com/AymanMoElhussiny/hello-remote.git
ayman@ubuntu-tst:~$ git remote -v
another https://github.com/AymanMoElhussiny/hello-remote.git (fetch)
another https://github.com/AymanMoElhussiny/hello-remote.git (push)
origin  https://github.com/AymanMoElhussiny/hello-remote.git (fetch)
origin  https://github.com/AymanMoElhussiny/hello-remote.git (push)
```
- you can pull any repo of that remote by its name like origin or another that mentioned 
```
ayman@ubuntu-tst:~$ git pull origin
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 9 (delta 0), reused 8 (delta 0), pack-reused 0
Unpacking objects: 100% (9/9), 1.17 KiB | 149.00 KiB/s, done.
From https://github.com/AymanMoElhussiny/hello-remote
 * [new branch]      improve-greeting -> origin/improve-greeting
 * [new branch]      main             -> origin/main
You asked to pull from the remote 'origin', but did not specify
a branch. Because this is not the default configured remote
for your current branch, you must specify a branch on the command line.
```
- you can fetch changes and updates from specif remote/branch not only the 
- remote name can be changed later by chaning record it self in [reponame]/.git/refs
- you can alway check difference between version and remote 
```
ayman@ubuntu-tst:~/hello-remote$ git diff origin/newbranch origin
diff --git a/file01.txt b/file01.txt
deleted file mode 100644
index e69de29..0000000
```
- note you cant delete branch you have to check to other branch also if not full merged you have to clarif with (-D) option
```bash
ayman@ubuntu-tst:~/hello-remote$ git branch -d newbranch 
error: Cannot delete branch 'newbranch' checked out at '/home/ayman/hello-remote'
ayman@ubuntu-tst:~/hello-remote$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.
ayman@ubuntu-tst:~/hello-remote$ git branch -d newbranch 
error: The branch 'newbranch' is not fully merged.
If you are sure you want to delete it, run 'git branch -D newbranch'.
ayman@ubuntu-tst:~/hello-remote$ git branch -D newbranch 
Deleted branch newbranch (was 0106710).
```
## 7. Tagging

Git tagging is a feature that allows you to mark specific points in Git history as important. Tags are typically used to capture a point in time that is used for a marked version release (e.g., software version numbers like v1.0.0). Unlike branches, tags in Git are immutable references, meaning they do not change once created.

- Tag is not a branch
- Why Use Tags?

1. **Release Versions:** Tags are commonly used to signify release points of software. This helps in easily identifying and accessing the codebase at the time of a particular release.

2. **Stable Points:** When your project reaches a stable and well-tested state, you can create a tag to mark that specific commit. This makes it easy to refer back to a known, stable state in the future.

3. **Collaboration:** Tags provide a way for collaborators to synchronize their work based on well-defined points in history, making collaboration more manageable.
   
### Types of Tags

1. Lightweighted Tags
A lightweight tag is simply a reference to a specific commit. It is created using the following command:

```bash
git tag <tag-name> <commit-hash>
```

## 8.merging
Merging in Git refers to the process of combining changes from one branch into another branch. It allows you to integrate the changes made in a feature branch, for example, back into the main branch (e.g., `master` or `main`). Merging is a fundamental operation in Git that helps bring different lines of development together.

Here are the key points about merging in Git:

8.1 **Branch Merging:**
   - Merging is often used when you have multiple branches in a Git repository, and you want to incorporate changes from one branch into another.
   - The most common scenario is merging changes from a feature branch back into the main branch.

8.2 **Merging Commands:**
   - To merge changes from one branch into another, you typically use the `git merge` command.
   - For example, to merge changes from a feature branch named "new-feature" into the current branch (usually `master` or `main`), you would do:

     ```bash
     git checkout master  # switch to the main branch
     git merge new-feature
     ```

   - This combines the changes made in the "new-feature" branch into the main branch.

8.3 **Fast-Forward Merge:**
   - If there are no conflicting changes between the branches, Git performs a "fast-forward" merge. This means that the branch pointer is simply moved forward, and no new commit is created.

8.4 **Three-Way Merge:**
   - In cases where there are conflicting changes (changes in both branches that cannot be automatically merged), Git performs a three-way merge. This involves creating a new commit that represents the combination of changes from both branches.

8.5 **Conflict Resolution:**
   - When a three-way merge encounters conflicting changes, Git marks the conflicting sections in the affected files and pauses the merge process.
   - You need to resolve the conflicts manually by editing the files and choosing which changes to keep.
   - After resolving conflicts, you complete the merge by staging the resolved files and running `git merge --continue`.

8.6 **Branch Deletion (Optional):**
   - After a successful merge, you might choose to delete the feature branch since its changes are now part of the main branch.

     ```bash
     git branch -d new-feature
     ```

8.7 **Graphical Merging Tools:**
   - Git also provides graphical merging tools that can assist in resolving conflicts. These tools allow you to visually compare and merge changes.

     ```bash
     git mergetool
     ```

Merging is an essential part of collaborative development in Git, allowing teams to work on features and bug fixes in isolation and then integrate their changes back into the main project. It helps maintain a clean and organized version history while facilitating parallel development efforts.

## 9.rebasing 
## 10. Undo 

## **Bonous tips**

## Resources 
- [McCullough and Berglund on Mastering Git ](http://docs.ptgels.com/)
