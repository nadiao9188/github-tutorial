# GitHub Tutorial

_by Nadia Ousman_

---
## Git vs. GitHub
Git and Github are great ways to manage and keep track of your code and most developers use them.
* Git is a version control system that keep "snapshots" (earlier versions) of code 
  * Runs in the command line
* Github is a website(cloud) that stores code on the internet
  * Runs in the command line  
  * You can visually track your changes from Git as well as other peoples changes on their projects
  * Makes collaborating on files easier

**_Git does not require Github but Github requires Git_**

---
## Initial Setup
You will be doing all of your work on the websites github and cloud9
#### To make a github account . . .
* Go to https://github.com/ (the github website)
* Click Sign up at the upper righthand side of the screen and fill in the information (Username, email address, and password )
* When you finish filling out this information in Step 1, click "Create an account" at the bottom of the screen and move on to Step 2
* Select the the free mode then click "Continue" to go to Step 3
  * The two boxes between these are optional. Read and select for your own liking
* Scroll to the bottom of the page and click "skip this step" 
 * Go to the email that you paired the accout with and open the conformation email and click the link in the email
 
**You now have a Github account!**

#### To create you cloud9 account . . .  
* Go to https://c9.io/login (the cloud9 website) and click the cat icon at the upper righthand side of the screen
* Login using you Github account and click "Sign in"
* Click "Authorize c9"
* Click "Sign in to Cloud9"
* Click the gear icon on the top-right of the screen then click "Connected Services"
* Connect Github by clicking "connect" on the Github section

**You now have a cloud9 account!**

#### To create a workspace . . .
* On the Cloud9 homepage, click " + Create a new workspace"
* Name the workspace "github-learning"
* Type "Version Control and Collaboration" as the description
* Select "Don't set a team for this workspace" in the Team section
* Select "Blank" as the template and click "Create Workspace"

After you have completed this, it is time to create an SSH key 

#### To create an SSH key . . .
* Go to your Github account and click your profile icon at the top-right corner of the screen
* Click "Settings"
* On the lefts sidebar, click "SSH and GPG"
* Click new "SSH keys" then "New SSH Key"
  * Title it "cloud9"
  * For the key section, go to your cloud9 account and click the gear icon on the top right
  * Go to "SSH keys tab" and copy and paste the second SSH key into the Key section (starts with **ssh-rsa**)
  * Click "Add SSH key"
* Open your new workspace and type in `ssh -T git@github.com` to the command line (It should say after "Hi <your username>! You've successfully authenticated, but GitHub does not provide shell access")

---
## Repository Setup
Now that you have all your accounts set up, it is time to make your first repository on cloud9 (repo for short).

#### To make your first repo on cloud9, type in the following to the command line (one at a time).
* `cd ~/workspace`
* `mkdir first-repo` (makes a new folder calles "first-repo")
* `cd first-repo` (Goes into the new folder)
* `git init` (this makes the folder a repository)  
**You now have your first repo!**

Now we have to create a remote. A remote repo is a repository on Github that allows you to store your code from you local repo (cloud9 in this scenario). It acts as a backup to your local repo.

#### To create a remote repo . . .
* Go to your github account and on the top-right, click the "+" sign and click "New repository"
* Name it the **exact same name** as a repo on your cloud9 that has the code you want to push (This is discussed in the Workflow and Commands section) to Github, or else it will not work
* Click "Create repository"
  * If you were asked to verify your email, do it. If it did not, continue to the next steps  
**You now have a remote repo!**

Now you have to make the bridge between Github and cloud9 so you can start pushing your commits.
#### To connect your local repo to your remote repo . . .
* Click "SSH" on the page that showed up after you clicked "Create repository"
* Copy and paste the lines under where it says "…or push an existing repository from the command line" into the command line on cloud9 one by one 
  * The first one should start with `git remote add origin ` and includes a URL at the end
  * The second one should be `git push -u origin master`

**You have now created the connection between your local and remote repos and can now make a repository in cloud9**


Now it is time to create your first file on your new cloud9 repo.  
#### To create your first README file . . .
* Type `touch README.md` into the command line.  
**You can now make changes in the file and add and commit them.**

#### To edit, add, and commit your file, one by one type into the command line . . .
* `c9 README.md` (opens the README file)
  * Type in anything you want in the opened file (Ex: "This is my first repo")
* `cd add README.md` (adds the new changes to the staging area to be commited)
* `git commit -m "create readme"` (Makes a snapshot of the current code)
  * In the quotation mark, write a message in the present-tense that relates to the changes you made. Ex: "Type my first line on README.md")
##### You have now made your first commit! 

---
## Workflow & Commands
#### Basic workflow of Git 
* You make a directory(folder) that contain other folders and files
  * Type in  `mkdir <intert name of directory>` 
* Initialize git in your directory by typing in `git init` in the command line. It then becomes a repository/repo 
  * Type in `git init` in the command line 
* You edit the files you made and save them
  * You can type in `git status` to show what files have been edited 
* Add the files to the stage
  * Type in `git add <insert file name>`
  * You can also use `git add .` to add the whole directory and `git add --all` to add all changes, including deleted files.
  * You can type `git status` to check if the file is on the stage
* Finally, you commit the files
  * Type in `git commit -m "<insert message>"`. The message should be in the present-tense and specifically describe what changes you made.
#### Basic workflow of Github
There are two workflows that you can use
1. Start at your repo on github
  * push
  * pull
  * clone
2. Start at someone elses repo on github
  * fork and clone
  * pull

---
## Rolling Back Changes







