

## Merge Conflict

How to resolve merge conflict.
When two features/developrs change and update code in same file.

Demo
 1. make a new branch `git checkout -b quick-test`
 2. modify code in index.html (quick-test branch )  ,save
 3. to dee modified or created files `git status`
 4. to see changes in files `git diff`
 5. ` git add .`  + `git commit -m "<commit message>"` 
 = `git commit -am "<commit message >"`(only for modified files , for new files you have to stage it first in order to git know about it )
 6. go back to main branch  `git checkout main` , no changes here from above
 7. now make changes in index.html (main branch ) , save 
 8. till here both branches are seperate , so no problem , what if we want to merge.
 9. try going back to quick-test branch `git checkout quick-test` ,this will give you error and not let you change branches , because there are local changes and it wil be over written. So we have to commit before changing branches.
 10.  `git status`
 11. `git commit -am "added there in main"`
 12. try again going back to quick-test branch `git checkout quick-test` , sucess
 13. `git diff main` , showes changes
 14.  now we  will merge main `git merge main` , now this will give merge conflict. Fix directly in code. 
 15. `git status`  then `git diff`
 16. we need to make another commit , of fixed merge conflict
 `git commit -am "merge in main , updated with main"`




logs:



    
     
    
    $ git branch
    * main
    
    
    $ git checkout -b quick-test
    Switched to a new branch 'quick-test'
    
    
    $ git branch
      main
    * quick-test
    
    
    $ git status
    On branch quick-test
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   Part 4/index.html
    
    no changes added to commit (use "git add" and/or "git commit -a")
    
    
    $ git diff
    diff --git a/Part 4/index.html b/Part 4/index.html
    index 34fa97d..5894bdc 100644
    --- a/Part 4/index.html 
    +++ b/Part 4/index.html 
    @@ -1 +1,2 @@
    -<div>Hello World</div>
    \ No newline at end of file
    +<div>Hello World</div>
    +<p>ramit</p>
    \ No newline at end of file
    
    
    $ git commit -am "add-and-commit for modified files only "
    [quick-test fefa406] add-and-commit for modified files only
     1 file changed, 2 insertions(+), 1 deletion(-)
    
    
    $ git checkout main 
    Switched to branch 'main'
    Your branch is up to date with 'origin/main'.
    
    
    $ git branch
    * main
      quick-test
    
    
    $ git checkout quick-test
    error: Your local changes to the following files would be overwritten by checkout:
            Part 4/index.html
    Please commit your changes or stash them before you switch branches.
    Aborting
    
    
    $ git status
    On branch main
    Your branch is up to date with 'origin/main'.
    
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   Part 4/index.html
    
    no changes added to commit (use "git add" and/or "git commit -a")
    
    
    $ git commit -am "added there in main"
    [main b7e29a7] added there in main
     1 file changed, 2 insertions(+), 1 deletion(-)
    
    
    $ git checkout quick-test
    Switched to branch 'quick-test'
    
    
    $ git diff main
    diff --git a/Part 4/index.html b/Part 4/index.html
    index de98e3b..5894bdc 100644
    --- a/Part 4/index.html 
    +++ b/Part 4/index.html 
    @@ -1,2 +1,2 @@
     <div>Hello World</div>
    -<p>there in main</p>
    \ No newline at end of file
    +<p>ramit</p>
    \ No newline at end of file
    
    
    $ git merge main
    Auto-merging Part 4/index.html
    CONFLICT (content): Merge conflict in Part 4/index.html
    Automatic merge failed; fix conflicts and then commit the result.
    
    
    $ git status
    On branch quick-test
    You have unmerged paths.
      (fix conflicts and run "git commit")
      (use "git merge --abort" to abort the merge)
    
    Unmerged paths:
      (use "git add <file>..." to mark resolution)
            both modified:   Part 4/index.html
    
    no changes added to commit (use "git add" and/or "git commit -a")
    
    
    $ git diff
    diff --cc Part 4/index.html
    index 5894bdc,de98e3b..0000000
    --- a/Part 4/index.html
    +++ b/Part 4/index.html
    @@@ -1,2 -1,2 +1,4 @@@
      <div>Hello World</div>
    - <p>ramit</p>
     -<p>there in main</p>
    ++<p>ramit</p>
    ++<p>there in main</p>
    ++
    
    
    $ git commit -am "merge in main , updated with main"
    [quick-test 93ff400] merge in main , updated with main
