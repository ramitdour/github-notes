
### **Quick setup**  — if you’ve done this kind of thing before

**or**

HTTP `https://github.com/ramitdour/github-notes.git`

SSSH `git@github.com:ramitdour/github-notes.git`

Get started by  [creating a new file](https://github.com/ramitdour/github-notes/new/main)  or  [uploading an existing file](https://github.com/ramitdour/github-notes/upload). We recommend every repository include a  [README](https://github.com/ramitdour/github-notes/new/main?readme=1),  [LICENSE](https://github.com/ramitdour/github-notes/new/main?filename=LICENSE.md), and  [.gitignore](https://github.com/ramitdour/github-notes/new/main?filename=.gitignore).

### …or create a new repository on the command line

    echo "# github-notes" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git branch -M main
    git remote add origin https://github.com/ramitdour/github-notes.git
    git push -u origin main

### …or push an existing repository from the command line

    git remote add origin https://github.com/ramitdour/github-notes.git
    git branch -M main
    git push -u origin main

### …or import code from another repository

You can initialize this repository with code from a Subversion, Mercurial, or TFS project.

[Import code](https://github.com/ramitdour/github-notes/import)

-----------------------------------------------------------------------

**Step 1 :** Cloning repo from github

Using SSH 
`git clone git@github.com:ramitdour/github-notes.git`


 on lunix type command `ls -la`
    This shows all the files and directories insite the present folder
   output:
   
	total 20
    
    drwxrwxr-x 4 ramitdour ramitdour 4096 Sep  6 20:35  .
    drwxrwxr-x 3 ramitdour ramitdour 4096 Sep  6 20:35  ..
    drwxrwxr-x 8 ramitdour ramitdour 4096 Sep  6 20:37  .git
    drwxrwxr-x 2 ramitdour ramitdour 4096 Sep  6 20:36 'Part 1'
    -rw-rw-r-- 1 ramitdour ramitdour  261 Sep  6 20:42  README.md

*.git file* contains all the data and version controlling on local machine 



-----------------------------------------------------------------------

**Step 2 :** Making new file and its status ,add ,commit, push

  

Create `index.html` , write something.

 `<div>hello world</div>`

Run `$ git status`


    On branch main
    Your branch is up to date with 'origin/main'.
    
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   README.md
    
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
            Part 1/index.html
    
    no changes added to commit (use "git add" and/or "git commit -a")


Observe : 
Modified files   `modified:   README.md`

Untracked   `Part 1/index.html`

Run >
`git add .` 
Track all of the untracked files
*or* 
`git add index.html` X
`git add Part 1/index.html`  X
`git add Part\ 1/index.html` this works because folder name contails white space 
To track specific file


Now 

    git status

output:

    On branch main
    Your branch is up to date with 'origin/main'.
    
    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            new file:   Part 1/index.html
    
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   README.md

Now *index.html* is Staged     `new file: Part 1/index.html`

to unstage run :  `git restore --staged Part\ 1/index.html"`


Now to Commit file run , -m is for message for this commit
`git commit -m "index.html Created"`
`git commit -m "index.html Created" -m "Descriction box text"`
o/p:

    [main 816841d] index.html Created
     1 file changed, 1 insertion(+)
     create mode 100644 Part 1/index.html


These changes are still on our local machine , not on out main git repo:

In order to push it to remote repository  run 
`git push`

o/p:

    Enumerating objects: 6, done.
    Counting objects: 100% (6/6), done.
    Delta compression using up to 8 threads
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (4/4), 392 bytes | 392.00 KiB/s, done.
    Total 4 (delta 0), reused 0 (delta 0)
    To https://github.com/ramitdour/github-notes.git
       1de2138..816841d  main -> main


Now the file/files are pused to remote repo. 




