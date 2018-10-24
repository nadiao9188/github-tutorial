# GitHub Tutorial

_by Nadia Ousman_

---
## Git vs. GitHub
Git and Github are great ways to manage and keep track of your code and most developers use them.
* Git is a version control system that keep "snapshots" (earlier versions) of code. 
  * Runs in the command line.
  * Use github to interact with other repositories
* Github is a website (cloud) that stores code on the internet.
  * You can visually track your changes from Git as well as other peoples changes on their projects.
  * Makes collaborating on files easier. 
     *   * Use github to interact with other repositories
     * You can start from someone elses repository using _fork_ and _clone_

**_Git does not require Github but Github requires Git._**

---
## Initial Setup
You will be doing all of your work on the websites github and cloud9.
#### To make a github account . . .
* Go to https://github.com/ (the github website).
* Click Sign up at the upper righthand side of the screen and fill in the information (Username, email address, and password ).
* When you finish filling out this information in Step 1, click "Create an account" at the bottom of the screen and move on to Step 2.
* Select the the free mode then click "Continue" to go to Step 3.
  * The two boxes between these are optional. Read and select for your own liking.
* Scroll to the bottom of the page and click "skip this step".
 * Go to the email that you paired the accout with and open the conformation email and click the link in the email.
 
**You now have a Github account!**

#### To create you cloud9 account . . .  
* Go to https://c9.io/login (the cloud9 website) and click the cat icon at the upper righthand side of the screen.
* Login using you Github account and click "Sign in".
* Click "Authorize c9".
* Click "Sign in to Cloud9".
* Click the gear icon on the top-right of the screen then click "Connected Services".
* Connect Github by clicking "connect" on the Github section.

**You now have a cloud9 account!**

#### To create a workspace . . .
* On the Cloud9 homepage, click " + Create a new workspace".
* Name the workspace "github-learning".
* Type "Version Control and Collaboration" as the description.
* Select "Don't set a team for this workspace" in the Team section.
* Select "Blank" as the template and click "Create Workspace".

After you have completed this, it is time to create an SSH key. 

#### To create an SSH key . . .
* Go to your Github account and click your profile icon at the top-right corner of the screen.
* Click "Settings".
* On the lefts sidebar, click "SSH and GPG".
* Click new "SSH keys" then "New SSH Key".
  * Title it "cloud9".
  * For the key section, go to your cloud9 account and click the gear icon on the top right.
  * Go to "SSH keys tab" and copy and paste the second SSH key into the Key section (starts with **ssh-rsa**).
  * Click "Add SSH key".
* Open your new workspace and type in `ssh -T git@github.com` to the command line (It should say after "Hi <your username>! You've successfully authenticated, but GitHub does not provide shell access").

---
## Repository Setup
Now that you have all your accounts set up, it is time to make your first repository on cloud9 (repo for short).

#### To make your first repo on cloud9, type in the following to the command line (one at a time).
* `cd ~/workspace`.
* `mkdir first-repo` (makes a new folder called "first-repo").
* `cd first-repo` (Goes into the new folder).
* `git init` (this makes the folder a repository).
**You now have your first repo!**

Now we have to create a remote. A remote repo is a repository on Github that allows you to store your code from you local repo (cloud9 in this scenario) to the cloud (github in this scenario). It acts as a backup to your local repo.

#### To create a remote repo . . .
* Go to your github account and on the top-right, click the "+" sign and click "New repository".
* Name it the **exact same name** as a repo on your cloud9 that has the code you want to push (This is discussed in the Workflow and Commands section) to Github, or else it will not work.
* Click "Create repository".
  * If you were asked to verify your email, do it. If it did not, continue to the next steps.  
**You now have a remote repo!**

Now you have to make the bridge between Github and cloud9 so you can start pushing your commits.

#### To connect your local repo to your remote repo . . .
* Click "SSH" on the page that showed up after you clicked "Create repository".
* Copy and paste the lines under where it says "…or push an existing repository from the command line" into the command line on cloud9 one by one .
  * The first one should start with `git remote add origin ` and includes a URL at the end.
  * The second one should be `git push -u origin master`.

**You have now created the connection between your local and remote repos and can now make a repository in cloud9**

Now it is time to create your first file on your new cloud9 repo.  

#### To create your first README file . . .
* Type `touch README.md` into the command line.  
**You can now make changes in the file, then add and commit them.**

#### To edit, add, and commit your file, one by one type into the command line . . .
* `c9 README.md` (opens the README file).
  * Type in anything you want in the opened file (Ex: "This is my first repo").
* `cd add README.md` (adds the new changes to the staging area to be commited).
* `git commit -m "create readme"` (Makes a snapshot of the current code).
  * In the quotation mark, write a message in the present-tense that relates to the changes you made. Ex: "Type my first line on README.md").
##### You have now made your first commit! 

---
## Workflow & Commands
#### Basic workflow of Git 
* You make a directory(folder) that contain other folders and files.
  * Type in  `mkdir <intert name of directory>`.
* Initialize git in your directory by typing in `git init` in the command line. It then becomes a repository/repo. 
  * Type in `git init` in the command line.
* You edit the files you made and save them.
  * You can type in `git status` to show what files have been edited.
* Add the files to the stage.
  * Type in `git add <insert file name>`.
  * You can also use `git add .` to add the whole directory and `git add --all` to add all changes, including deleted files.
  * You can type `git status` to check if the file is on the stage.
* Finally, you commit the files.
  * Type in `git commit -m "<insert message>"`. The message should be in the present-tense and specifically describe what changes you made.

#### Basic workflow of Github
There are two workflows that you can use
1. Start at your repo on github.
  * push
  * pull
  * clone
2. Start at someone elses repo on github.
  * fork and clone
  * pull

#### Most used Git commands 
* `git status`:  See which files have been edited since the last commit you made. Files that have been changed or files that are new to the timeline are in red. Files in the stage are in green.

* `git add <filename>.txt`: Add files to the staging area.
  * `filename.txt` - Instead of "filename", type the actual name of your file.

* `git commit -m "<insert message>"`: Take a “snapshot” of the files/saves your current code on the stage. The message should be in present-tense, describe what you changed, and be short and specific (Ex: "create ‘HTML’ template"). 

* `git push -u origin master`: Sends your most current commit to your remote repo.
  * `push` sending commits to remote repo.
  * `-u`- tells git to remember what remote repo you want to push to.
  * `origin`- the remote we are pushing to.
  * `master`- the “main” branch of our project.

---
## Rolling Back Changes

If you want do undo a step that you took, there are different commands that you can use to undo them, depending on what step you are on now and what step you want to go back to.

* `git checkout -- <filename>.txt`: Undo your edits you made to your file (edit->start).

* `git reset HEAD <filename>.txt`: Undo adding your file to the stage (add->edit).

* `git reset --soft HEAD ~1`: Undo commiting your file (commit->add).

* `git reset HEAD~1`: Undo commiting and adding your file at the same time (commit->add->edit).

* `git reset --hard HEAD~1`: Undo commiting and adding your file, as well as undoing your edits you made to your file at the same time (commit->add->edit->start).

* `git revert <commit sha>`: Undo a specific commit you made (commit->add).
  * ``commit sha` - list of numbers and letters that defines a specific commit you made. You can get this list by typing in `git log`, which will list all the commits that you have made with the corresponding commit sha.

* `git reset --hard <insert commit sha>`: Undo pushing a certain file to the remote repo, commiting, adding, and editing/start from the beginning (push->commit->add->edit->start).
  

* `git push origin +master`: Undo pushing all your files to the remote repo, commiting, adding, and editing/start from the beginning (push->commit->add->edit->start).

---
## Markdown Syntax
This section's contents is meant to be used in files when editing them. This makes what you are typing more organized by controling what is displayed on the file.
#### Italics
* To make a phrase italic in Markdown, you can surround words with an underscore (_). For example, `_this_` would become italic and look like _this_.
#### Bold
* To make phrases bold in Markdown, surround the words you want bolded with two asterisks (**). The word "text" woud become **text** by typing in `**text**`.
  * To make text bold and italic, combine the two by typing both underscores and double asterisks (`**_text_**`).
#### Headers
* Add a `#` before the text you want to become a header.
  * The amount of headers you use changes the size of it. For example if you add only one `#`, the text will be the biggest size it can be (Header 1). If you add six `#`, the text will be the smallest size it can be (Header 6).

#### Links
There are two ways to insert links, inline and reference links.
* Inline links: This kind of link makes a line of text clickable and when you click it, it sends you to the link you set it to. 
  * Wrap the link text (text you want to be clickable) in brackets, and wrap the actual link in parenthesis. (to create a link to `www.google.com`, with a link text that says, `Visit Google!`, type `[Visit Google!](www.google.com)`.
  * Reference links: The link text is a reference to another place in the file, where the actual link is.
    * Reference links would look like this when typed in the file

```
[Link to Google][Google]  
[Link to Github][Github]
 
  
Other code
 
  
[Google]: www.google.com
[Github]: www.github.com
```
#### Images
Like headers, there are also two different ways to include images, inline image links and reference images.
* Inline image links:
  * Type `!`, wrap your alt text in brackets, and wrap your link in parenthesis. (Ex: `![<insert alt text>](image link)`).
  * alt text is a description of the image.
* Reference image:
  * Same pattern as a reference link but type `!` in front of the alt text and the link will be the image link. 

#### Blockquotes
* Blockquotes is a sentence or paragraph that that is formatted to stand out to the reader. These are usually quotes from another source.
  * Type a greater than sign,`>`, before the line.
  * You can use this on each line of a quote if it spans over multiple sentences or paragraphs.

#### Lists
* There are two different kinds of lists, unordered and ordered.
  * Unordered lists: lists that use bullet points.
    * Type `*` and a space in between the asterisk and the line.
    * You can nest one list in another by indenting the asterisk one spance more than the one before it 
  * Ordered lists: lists that are numbered.
    * Type `1.` and a space inbetween the number and the line. Depending on how long the list is, you can change the number to match the number of the line. 
  * If you want to include paragraphs in your lists, the paragraphs have to start on a seperate line and it has to be indented by at least one space

#### Paragraphs
* For poems:
  * Make an empty line in between each line of text: This is called a **hard break**
  * Inserting two spaces after each new line. is called a **soft break**

#### Inserting Code
* To format text like code, you use backticks before and after the text
  * Inline code snippet: ``` `<insert text>` ```
  * Multiline code snippet: ` ```<insert text>``` `

#### Other things to know
* Creating a line in between text: ---
  * Hat to be on its own line 