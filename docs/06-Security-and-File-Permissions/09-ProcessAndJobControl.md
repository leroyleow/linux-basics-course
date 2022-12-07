# Proces And Job Control

To display the currently running processes use the ps command. 

Common ps commands:

ps -e -> Display all processes.
ps -ef -> Display all processes
ps -eH -> Display a process tree
ps -e --forest -> Display a process tree
ps -u username -> Display processes running as username

## Running Processes in the Foreground and Background

When a command process, or program is running programs the shell prompt will not be displayed until that process exists. For long running programs, it is good to send them to background. To start background a process, place an ampersand (&) at the end of the command.

```
command & -> Start command in the background

Ctrl-c -> Kill the foreground process

Ctrl-z -> Suspend the foreground process

bg [%num] -> Background a suspend process

fg [%num] -> Foregronud a background process

kill [%num] -> Kill a process by job number or PID

job [%num] -> List jobs.
```

## Killing Processes
```
Ctrl-c -> Kill the foreground process

kill [signal] pid -> Send a signal to a process

kill -l -> Display a list of signals
```