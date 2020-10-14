# Working with predefined (private/ public) repo

Here you will see how you can use `git`. `git` is a command line tools used for
version controlling.

## Tools
Use `Git Bash` for Windows and `git` for Ubuntu.

## Instructions
**1.** Intsall `Git Bash` for Windows/ `git` for Linux and configure it as follow:
```bash
git config --global user.name "your_username"
git config --global user.email your_email

# Note: Make sure you have github account with this username and email.
```

**2.** Open `Git Bash`/ terminal and clone the repo in your desired directory.
```bash
git clone "HTTPS URL of git repo"
```

**3.** Now go to repo folder using `cd` command.
```bash
cd "repo_master_folder"
```

**4.** Now add or delete or modify the files and folders.

**5.** Use `status` command to see the status.
```bash
git status
```

**6.** Use `add` command to add folder/ files.
```bash
git add <Folder/ File>
```

**7.** Use `rm` command to remove the folder/ files.
```bash
git rm -r <Folder/ File>
```

**8.** Now commit the changes as follow.
```bash
git commit -a -m your_message
# Here if you are not giving your message for commit then commit will be aborted.
```

**9.** Finally Push your master brach to origin.
```bash
git push
```
