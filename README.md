## Notes for Git
I am tring to collect note for a wonderful course for git 
*McCullough and Berglund on Mastering Git*

### 06 remote
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

## links
- [McCullough and Berglund on Mastering Git ](http://docs.ptgels.com/)
