

## Git branch

Run to get current branch  
`git branch`

To create new branch
`git checkout -b <branch-name>`

Switch between branch 
`git checkout <branch-name>`

logs:

    $ git branch
    * main
    
    $ git checkout -b feature-readme-instruction
    Switched to a new branch 'feature-readme-instruction'
    
    $ git branch
    * feature-readme-instruction
      main
    
    $ git checkout master
    error: pathspec 'master' did not match any file(s) known to git
    
    $ git checkout main
    Switched to branch 'main'
    Your branch is up to date with 'origin/main'.
    
    $ git branch
      feature-readme-instruction
    * main
    
    $ git checkout feature-readme-instruction 
    Switched to branch 'feature-readme-instruction'
    

1.Switch/ checkout to feature branch 
2.make some changes to README.md and save file
3.check status `git status`
4.stage changes by `git add .`
5.check status again  `git status`
6.commit the code `git commit -m "updated readme" -m "description"`

7.switch to main branch `git checkout main` observe changes 
8.to see differances `git diff feature-readme-instruction`

9.switch back to feature branch `git checkout feature-readme-instruction `
10.try pushing  the commited branch to git `git push` , this will give error.
because up stream is not set. do below.
    
11.`git push --set-upstream origin feature-readme-instruction`
   same as (or)
   `git push -u origin feature-readme-instruction`



logs :

    
    $ git branch
    * feature-readme-instruction
      main
    
    
    $ git status
    On branch feature-readme-instruction
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
      (use "git restore <file>..." to discard changes in working directory)
            modified:   README.md
    
    no changes added to commit (use "git add" and/or "git commit -a")
    
    
    $ git add .
    
    
    $ git commit -m "updated readme" -m "description"
    [feature-readme-instruction 59dc0ae] updated readme
     1 file changed, 6 insertions(+)


    $ git checkout main 
    Switched to branch 'main'
    Your branch is up to date with 'origin/main'.
    

    $ git checkout feature-readme-instruction 
    Switched to branch 'feature-readme-instruction'


    $ git checkout main 
    Switched to branch 'main'
    Your branch is up to date with 'origin/main'.


    $ git branch
      feature-readme-instruction
    * main


    $ git diff feature-readme-instruction 
    diff --git a/README.md b/README.md
    index be0e7d0..ceb5688 100644
    --- a/README.md
    +++ b/README.md
    @@ -15,9 +15,3 @@ This repo contains notes of git use.
     
     Description 
     
    -## Local development
    -
    -For for feature-readme-instruction branch
    -
    -1. Open index.html in your browser
    -
    
    
    $ git checkout feature-readme-instruction 
    Switched to branch 'feature-readme-instruction'
    ramitdour@ramitdour-System-Product-Name:~/Desktop/thispc/vsc_projects/github-notes$ git status
    On branch feature-readme-instruction
    nothing to commit, working tree clean


    $ git push
    fatal: The current branch feature-readme-instruction has no upstream branch.
    To push the current branch and set the remote as upstream, use
    
        git push --set-upstream origin feature-readme-instruction
    


    $ git push --set-upstream origin feature-readme-instruction
    Enumerating objects: 5, done.
    Counting objects: 100% (5/5), done.
    Delta compression using up to 8 threads
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 386 bytes | 386.00 KiB/s, done.
    Total 3 (delta 2), reused 0 (delta 0)
    remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
    remote: 
    remote: Create a pull request for 'feature-readme-instruction' on GitHub by visiting:
    remote:      https://github.com/ramitdour/github-notes/pull/new/feature-readme-instruction
    remote: 
    To https://github.com/ramitdour/github-notes.git
     * [new branch]      feature-readme-instruction -> feature-readme-instruction
    Branch 'feature-readme-instruction' set up to track remote branch 'feature-readme-instruction' from 'origin'.

------------------------------------------------------------------------------------------
go to github repo on your browser , 
git_branch 4.png

compare and & pull request

git_branch5.png

merge pull request
confirm changes

git_branch6.png

now we can see feature branch changes into main branch on github only

------------------------------------------------------------------------------------------

now locally switch back to main branch `git checkout main`

as you can seemerge changes are not visiable on loacal machine 
those merge changes are only on git.
we need to get those changes on loacl envt , by pulling them

`git pull  origin main` if upstream not set 
( to check current upstream `git remote show origin` or  `git branch`)
or
`git pull`

now local main branch will also be updated 

logs :


    $ git checkout main
    Switched to branch 'main'
    Your branch is up to date with 'origin/main'.
    
    
    $ git status
    On branch main
    Your branch is up to date with 'origin/main'.
    
    nothing to commit, working tree clean
    
    
    $ git status -v
    On branch main
    Your branch is up to date with 'origin/main'.
    
    nothing to commit, working tree clean
    
    
    $ git remote show origin
    * remote origin
      Fetch URL: https://github.com/ramitdour/github-notes.git
      Push  URL: https://github.com/ramitdour/github-notes.git
      HEAD branch: main
      Remote branches:
        feature-readme-instruction tracked
        main                       tracked
      Local branches configured for 'git pull':
        feature-readme-instruction merges with remote feature-readme-instruction
        main                       merges with remote main
      Local refs configured for 'git push':
        feature-readme-instruction pushes to feature-readme-instruction (up to date)
        main                       pushes to main                       (local out of date)
    
    
    $ git pull
    remote: Enumerating objects: 1, done.
    remote: Counting objects: 100% (1/1), done.
    remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
    Unpacking objects: 100% (1/1), 640 bytes | 640.00 KiB/s, done.
    From https://github.com/ramitdour/github-notes
       7c719ae..7c760c8  main       -> origin/main
    Updating 7c719ae..7c760c8
    Fast-forward
     README.md | 6 ++++++
     1 file changed, 6 insertions(+)

------------------------------------------------------------------------------------------
### deleting old feature branch (after it is merged )

`git branch -d <feature-branch-name>`

logs:

    $ git branch
      feature-readme-instruction
    * main
    
    $ git branch -d feature-readme-instruction 
    Deleted branch feature-readme-instruction (was 59dc0ae).
    
    $ git branch
    * main
