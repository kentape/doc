# doc
#Various documentation

## toc

- [doc](#doc)
  - [toc](#toc)
  - [Markdown syntax](#markdown-syntax)
  - [Mule](#mule)
    - [MUnit](#mUnit)
    - [Regex](#regex)
  - [Postman](#postman)
  - [Maven](#maven)
  - [GIT](#git)
    - [Various commands](#various-commands)
    - [Track remote branches](#track-remote-branches)
    - [Create repository from existing project](#create-repository-from-existing-project)
  - [Terminals](#terminals)
  - [Ubuntu](#ubuntu)
    - [Sökningar](#sökningar)

### Markdown syntax
* https://guides.github.com/features/mastering-markdown/

## Mule

- [Java Code Examples for org.mule.api.MuleMessage](https://www.programcreek.com/java-api-examples/?api=org.mule.api.MuleMessage)
- [Java Code Examples for org.mule.api.MuleEvent](https://www.programcreek.com/java-api-examples/?api=org.mule.api.MuleEvent)
- [Configuring Properties](https://docs.mulesoft.com/mule-runtime/3.9/configuring-properties)
- [Loading property file](https://forums.mulesoft.com/questions/95658/loading-property-file.html)
- [How to read properties into JAVA code from properties file in mule?](https://forums.mulesoft.com/questions/77979/how-to-read-properties-into-java-code-from-propert.html)

### MUnit
- [MUnit Maven Plugin](https://docs.mulesoft.com/munit/2.3/munit-maven-plugin)
- [Coverage](https://docs.mulesoft.com/munit/2.3/munit-coverage-report)
- [About Assert That Event Processor](https://docs.mulesoft.com/munit/2.1/assertion-message-processor)
- [MUnit Tests with Java](https://docs.archive.mulesoft.com/munit/v/1.1/munit-tests-with-java)

### Regex

```#[(flowVars.scp.matches('^[a-zA-Z0-9]*$') == false)]```
Tillåter små bokstäver mellan a-z, stora bokstäver mellan A-Z samt siffror mellan 0-9
Tillåter obegränsat antal tecken

```#[(flowVars.scp.matches('^[a-zA-Z0-9]{1,30}$') == false)]```
Tillåter små bokstäver mellan a-z, stora bokstäver mellan A-Z samt siffror mellan 0-9
Strängen får vara mellan 1 till 30 tecken lång

```#[(flowVars.scp.matches('^[a-zA-Z0-9]{50}$') == false)]```
Tillåter små bokstäver mellan a-z, stora bokstäver mellan A-Z samt siffror mellan 0-9
Strängen måste vara exakt 50 tecken lång

## Postman
Problem med anrop pga 403 Forbidden, "invalid csrf token"
  - [ref](https://i.stack.imgur.com/ab71y.png)
  - Leta upp en Cookie som heter XSRF-TOKEN i Responset
  - Skapa en header med namnet XSRF-TOKEN och sätt den till värdet från cookien ovan
  - gör ett nytt requeste så bör det funka

## Maven

- [Using Maven within the Eclipse IDE - Tutorial](http://www.vogella.com/tutorials/EclipseMaven/article.html)
- [Dependency Scope](http://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html#Dependency_Scope)
- [POM Reference](https://maven.apache.org/pom.html)

<br>

Maven always uses either one or two settings files. The global settings defined in (${M2_HOME}/conf/settings.xml) is always required.
The user settings file (defined in ${user.home}/.m2/settings.xml) is optional. Any settings defined in the user settings take precedence
over the corresponding global settings.
You can override the location of the global and user settings from the command line, the following example will set the global settings
to c:\global\settings.xml and the user settings to c:\user\settings.xml:

```markdown
mvn install --settings c:\user\settings.xml 
    --global-settings c:\global\settings.xml
```
	
```rtMaven.opts = "-Dmaven.repo.local=${local_mvn_repo} -Djavax.net.ssl.trustStore=/opt/oracle/java/jdk-1.8.0.121.1/jre/lib/security/cacerts -DskipTests=false"```

```mvn dependency:tree```
  
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

## Ubuntu

### Sökningar
```zgrep 195904272399 audit/*.log.gz```

```zgrep 4e499d80-9196-11e9-8e00-005056814864 audit/*.log.gz```

```grep 195904272399 audit/*.log```

```zgrep -R --include=*.gz -H "foretag" .```

```zcat -r /opt/mulesoft/icc/rt05-pro/mule/logs | grep "Ogiltigt clientID"```
