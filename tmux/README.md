# Remote connection management with tmux.


## Pre - requisite
Install **tmux** on Linux.


## Importance of

tmux is a very neccessary tool if you want to keep running some big tasks
remotely in background even if your session is ended.
The practical use cases of tmux can be in following scenarios:
1. When your internet connection is not reliable and you want to do some big
downloads/ installations/ compilations remotely with full safety.
2. You want to end your session but want to keep running something on remote
machine.


## Commands

1. To start a tmux session
> **tmux new -s some_session_name**
> This will open new terminal Window for this session.

2. To Dettach current session from the current using terminal (shell)
> **Press Ctrl + b then d**
> This will dettach current tmux session and the created Window will be closed.

3. To attach current using terminal (shell) to a **tmux session**
> **tmux attach -t some_session_name**
> This will open new Windows with a session.

4. To kill a tmux session
> **tmux kill-session -t some_session_name**
> This will kill a tmux session.

5. To list all running sessions
> **tmux ls**


## Practical use

First start a tmux session let say **tmux_big_task_1** then run your desired
background / big task in this window and then while running press **Ctrl + b**
then **d** to dettach it from the current session. Now if you exit from ssh
connection and reconnect, you will see your tmux session is running and you can
see what's going on by attaching to your current terminal (shell).
Beautiful, right?
