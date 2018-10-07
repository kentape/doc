# doc
#Various documentation

### Markdown syntax:
* https://guides.github.com/features/mastering-markdown/
  
## GIT
### Various commands
* cache credentials
   * $ git config credential.helper cache
   
### Track remote branches
* When you're starting to work on an existing remote branch (tracka en remote branch)
   * Branch dev set up to track remote branch dev from origin. Switched to a new branch 'dev'
   * $ git checkout --track origin/dev
*  When you're publishing a local branch
   * you started a new local branch and now want to publish it on the remote for the first time
   * git push -u origin dev __eller__ git push --set-upstream origin dev

### Create repository from existing project.  
Refs:
* https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/
  
#### Preconditions:
* jag har påbörjat ett projekt, t ex ett Mule projekt
* kommer på att jag vill versionshantera detta efter en tids utvecklingsarbete

#### Step-by-step
1. Skapa ett nytt tomt repository i GitHub (utan README etc.)
   1. ex: errorHandling
2. Gå till projektet
   1. $ cd /mnt/c/kenta/dev/ws/ap644/errorhandling
   1. $ git init
   1. $ git add .
   1. $ git commit -m "First commit"
   1. $ git remote add origin remote repository URL
   1. $ git remote -v
   1. $ git push origin master
   1. $ git push -u origin dev __eller__ git push --set-upstream origin master (för att ange att man vill tracka den nya remota branchen)
