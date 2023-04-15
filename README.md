# continuous-integration-jenkins
## A project to demonstrate continuous integration using Jenkins

### Requirements:
* Integrate jenkins to work with GIT
* Install MAVEN on the local machine
* Generate Maven project

### Maven project
* Generate a project (mvn archetype:generate) 
* group Id (package name) example com.testing.sample, org.test.sample
* artifactId (name of your project), example: myApp
* version (The default is 1.0)
* package (The supplied groupid)

see the file "Generating maven project" for more details.

### The Project

Generate a Maven project on your local machine

Push to a remote repo such as Github

Integrate your Jenkins server with Github

Configure the Jenkins server to build project with Maven 

#### Create a freestyle project with the following settings:

* SCM: select Git and provide the URL for the repository
* Build steps: "Invoke top-level Maven targets" and define  a goal such as: test, install, clean, package ...
Proceed to the advance section and enter the pom.xml path directory.
* Build Triggers: "Poll SCM"(set appropriate CRON for the schedule) or "GitHub hook trigger for GITScm polling"(set up webhook on GitHub)

### Automation
On the local repo, create a new branch, make changes to the test cases, test the change locally
push the branch to the remote repo. 
Go to Jenkins server, select a desired trigger and switch to the new branch. Wait for jenkins to build the
job automatically. explore the automation process by making other changes on the local repo and pushing to the remote repository.

Finally, create a pull request and merge the newly created branch to the main branch.
