# doc
#Various documentation

### Markdown syntax:
* https://guides.github.com/features/mastering-markdown/
  
  
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
