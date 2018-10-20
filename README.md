# GitHub Tutorial

_by Nadia Ousman_

---
## Git vs. GitHub
* Git is a version control system that keep snapshots (earlier versions) of code 
  * Runs in the command line
* Github stores code in the cloud (the internet) 
  * You can visually track your changes on Git
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
Now that you have all your accounts set up, it is time to make your first repository on cloud9 (repo for short). But before you do this, we have to create a remote.  
A remote repo is a repository on Github that allows you to store your code from you local repo (cloud9 in this scenario). It acts as a backup to your local repo.

#### To create a remote repo . . .
* Go to your github account and on the top-right, click the "+" sign and click "New repository"
* Name it the **exact same name** as a repo on your cloud9 that has the code you want to push (This is discussed in the Workflow and Commands section) to Github, or else it will not work
* Click "Create repository"
  * If you were asked to verify your email, do it. If it did not, continue to the next steps

**You now have a remote repo!**

Now you have to make the bridge between Github and cloud9 so you can start pushing your commits.
* Click "SSH" and where it says "…or push an existing repository from the command line", copy and paste the lines under it into the command line on cloud9 one by one


**You have now created the connection between your local and remote repos and can now make a repository in cloud9**

#### To make your first repo, type in the following to the command line (one at a time)
* `cd ~/workspace`
* `mkdir first-repo` (makes a new folder calles "first-repo")
* `cd first-repo` (Goes into the new folder)
* `git init` (this makes the folder a repository)

**You now have your first repo!**

#### Creating your first repo . . .
To create your first README file, all you have to do is to type the command  `touch README.md` into the command line. 
#### To edit, add, and commit your file, one by one type into the command line . . .
* `c9 README.md` (opens the README file)
  * Type in anything you want in the opened file (Ex: "This is my first repo")
* `cd add README.md` (adds the new changes to the staging area to be commited)
* `git commit -m "create readme"` (Makes a snapshot of the current code)
  * In the quotation mark, write a message in the present-tense that relates to the changes you made. Ex: "Type my first line on README.md")
##### You have now made your first commit! 

---
## Workflow & Commands



---
## Rolling Back Changes







