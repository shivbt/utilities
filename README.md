# Working with predefined (private/ public) repo

## Tools
Use Git Bash for Windows and git for Ubuntu.

## Instructions
**1.** Open Git Bash/ git terminal and clone the repo in your desired folder.
> **git clone "HTTPS URL of git repo"**

**2.** Now go to repo folder using "cd" command.
> **cd "repo_master_folder"**

**3.** Now add or delete or modify the files and folders.

**4.** Use **status** command to see the status.
> **git status**

**5.** Use **add** command to add folder/ files.
> **git add <Folder/ File>**

**6.** Use **rm** command to remove the folder/ files.
> **git rm -r <Folder/ File>**

**7.** Now commit the changes as follow.
> **git commit -a -m your_message**
> **Note:**
> Here if you are not giving your message for commit
> then commit will be aborted.

**8.** Finally Push your master brach to origin.
> **git push**
