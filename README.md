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
## 3. Cloning
## 4. Storage and hashs
## 5. Branches


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
## 8.
## 9. 
## 10. Undo 

## **Bonous tips**

## Resources 
- [McCullough and Berglund on Mastering Git ](http://docs.ptgels.com/)
