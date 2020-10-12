# Working with predefined (private/ public) repo

## Tools
Use Git Bash for Windows and git for Ubuntu.

## Instructions
**1.** Intsall Git Bash for Windows/ git for Linux and configure it as follow:
> **git config --global user.name "your_username"**

> **git config --global user.email your_email**

> **Note:** Make sure you have github account with this username and email.

**2.** Open Git Bash/ git terminal and clone the repo in your desired folder.
> **git clone "HTTPS URL of git repo"**

**3.** Now go to repo folder using "cd" command.
> **cd "repo_master_folder"**

**4.** Now add or delete or modify the files and folders.

**5.** Use **status** command to see the status.
> **git status**

**6.** Use **add** command to add folder/ files.
> **git add <Folder/ File>**

**7.** Use **rm** command to remove the folder/ files.
> **git rm -r <Folder/ File>**

**8.** Now commit the changes as follow.
> **git commit -a -m your_message**
> **Note:**
> Here if you are not giving your message for commit
> then commit will be aborted.

**9.** Finally Push your master brach to origin.
> **git push**
