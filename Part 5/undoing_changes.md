

## Undoing commits and staged changes

#### Undoing staged changes 

 1. `git branch`
 2. `git status`
 3. `git add.` or `git add filename-with-extension`
 4. `git status`
 5. `git reset` or `git reset filename-with-extension`
 6. `git status`

logs:

    $ git branch
    * main
      quick-test
    
    
    $ git status
    On branch main
    Your branch is up to date with 'origin/main'.
    
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   Part 5/README.html
    
    no changes added to commit (use "git add" and/or "git commit -a")
    
    
    $ git add Part\ 5/README.html
    
    
    $ git status
    On branch main
    Your branch is up to date with 'origin/main'.
    
    Changes to be committed:
      (use "git restore --staged <file>..." to unstage)
            modified:   Part 5/README.html
    
    
    
    $ git reset
    Unstaged changes after reset:
    M       Part 5/README.html
    
    
    $ git status
    On branch main
    Your branch is up to date with 'origin/main'.
    
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   Part 5/README.html
    
    no changes added to commit (use "git add" and/or "git commit -a")


#### Undoing comitted changes

 1.  `git add Part\ 5/README.html` or `git add .`
 2.  `git commit -m "added install step"`
 3.  `git status`
 4.  `git reset HEAD~1` reset the last commit to staged 
 5.  `git status`
 6.  `git diff`
 7.  `git log`
 8.  `git reset <hash of commit>` to set specific commit , changes will be unstaged 
 9.  `git reset --hard <hash of the commit>` not only unstage but will also completely remove 
 
