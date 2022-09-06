

## Git repo from local machine

In part 1 we have created the repo from web client/ git hub website thec cloned it to our local machine.

Now we will create repo first on local machine then pust it to git.

Create new folder.

    cd  <git folder>
    git init
    git status
    add .
    git status
    git commit -m "created readme" - m "description"
    git push origin main 

o/p error:

    fatal: 'origin' goesnot appaer to be a git repository
    fatal: Coud not read from remote repo
    
Because these is no such repo on git , this is on loacal machine
We have to create that connection 

Now create empty git repo on github with same name `<git folder>`

`git remote add origin git@github.com:ramitdour/<git folder/repo name>.git`
`git remote -v` shows connected repo 
`git push origin main ` 

If not writing `git push origin main `  everytime set upstream first by below command 

`git push -u origin main ` this sets up stream now below command will work properly 

`git push`



![Git flow ](https://github.com/ramitdour/github-notes/blob/main/Part%202/git_init_flow.png?raw=true)

        
    
