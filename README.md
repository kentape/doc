# doc
#Various documentation

## toc

- [doc](#doc)
  - [toc](#toc)
  - [Markdown syntax](#markdown-syntax)
  - [Mule](#mule)
    - [MUnit](#mUnit)
  - [Postman](#postman)
  - [GIT](#git)
    - [Various commands](#various-commands)
    - [Track remote branches](#track-remote-branches)
    - [Create repository from existing project](#create-repository-from-existing-project)
  - [Terminals](#terminals)

### Markdown syntax
* https://guides.github.com/features/mastering-markdown/

## Mule

### MUnit
- [MUnit Maven Plugin](https://docs.mulesoft.com/munit/2.3/munit-maven-plugin)
- [Coverage](https://docs.mulesoft.com/munit/2.3/munit-coverage-report)

## Postman
Problem med anrop pga 403 Forbidden, "invalid csrf token"
  - [ref](https://i.stack.imgur.com/ab71y.png)
  - Leta upp en Cookie som heter XSRF-TOKEN i Responset
  - Skapa en header med namnet XSRF-TOKEN och sätt den till värdet från cookien ovan
  - gör ett nytt requeste så bör det funka
  
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

### Create repository from existing project
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

## Terminals
### Terminator
* https://terminator-gtk3.readthedocs.io/en/latest/index.html
