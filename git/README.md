# Working with predefined (private/ public) repo

Here you will see how you can use `git`. `git` is a command line tools used for
version controlling.

## Tools
Use `Git Bash` for Windows and `git` for Ubuntu.

## Normal Workflow

Configuring git and doing push & pull. <br/>

**1.** Intsall `Git Bash` for Windows/ `git` for Linux and configure it as follow:
```bash
$ git config --global user.name "your_username"
$ git config --global user.email your_email

# Note: Make sure you have github account with this username and email.
```

**2.** Open `Git Bash`/ terminal and clone the repo in your desired directory.
```bash
$ git clone "HTTPS URL of git repo"
```

**3.** Now go to repo folder using `cd` command.
```bash
$ cd "repo_master_folder"
```

**4.** Now add or delete or modify the files and folders.

**5.** Use `status` command to see the status.
```bash
$ git status
```

**6.** Use `add` command to add folder/ files.
```bash
$ git add <Folder/ File>
```

**7.** Use `rm` command to remove the folder/ files.
```bash

#1. Removing file
$ git rm <FileName>

#2. Removing folder
$ git rm -r <FolderName>

```

**8.** Now commit the changes as follow.
```bash

#1. Commit with single line comment.
$ git commit -m "your_message"

#2. Commit with mutiline comment [One Way]
$ git commit -m "your_message_1" -m "your_message_2"

# Note: Here if you are not giving your message for commit then commit will be aborted.
```

**9.** Finally Push your master brach to origin.
```bash
$ git push
```

**10.** To see all commits use following command. You will all commits done so
far. If you have lot of commits press `ENTER`, to see all and press `q` to exit.
```bash
$ git log
```
## Advance Workflow

Handling branches. <br/>

**1.** Listing branches.
```bash

#1. Listing branches on local machine
$ git branch --list

#2. Listing all branches (local and remote)
$ git branch --all

```

**2.** Creating and selecting the branch.
```bash

# [One Way] Create branch on local machine and go to that branch
$ git branch your_branch_name
$ git checkout your_branch_name

# [Other way] ...
$ git checkout -b your_branch_name

# After running this command you will be on the branch "your_branch_name", so
# any changes (file modifications) made, will be visible in this branch only.

```

**3.** Now do the file changes (updation) in that branch and push it to the
remote (github.com or other git hosting site).
```bash

# If you run git push without setting remote branch name it will through
# following error.
$ git push
fatal: The current branch <YourBranchName> has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin <YourBranchName>

# So, set upstream with push
$ git push --set-upstream origin <YourBranchName>

# Now you can perform modifications in that branch and push it to remote
# as normal git push & pull

```

**4.** Now if you want to work with that branch on some other machine.
```bash

# 1. Do git pull, it will bring all branches and updated main branch on your machine
$ git pull

# 2. Now if you want to work on that branch, run
$ git checkout -b your_branch_name

# 3. Do git pull again (after switching to that branch in step 2), it will
# through following error.
$ git pull
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<branch> <YourBranchName>

# 4. So let's set up upstream and again do git pull, now it will bring all
# changes to your local machine.
$ git branch --set-upstream-to=origin/your_branch_name your_branch_name
$ git pull


```

**5.** Deleting the branch.
```bash

# Deleting the branch locally only
$ git branch -d your_branch_name

# Deleting the branch both locally and remotely
$ git branch -rd origin/your_branch_name

```
