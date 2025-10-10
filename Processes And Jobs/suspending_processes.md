# pwn.college_garvit
# Processes and Jobs

# Suspending Processes
This challenge teaches how to suspend a process to the background using the ctrl-z hotkey, which is a less drastic measure than interrupting with ctrl-c. The /challenge/run program will only give the flag if it sees another copy of me running in this terminal. The solution is to launch it, then suspend it, then launch another copy while the first is suspended.

### Solve
**Flag:** `pwn.college{UDX0QhixyJQ2VFFj8CRYgFluf6T.QX1QDO0wSN0AzNzEzW}`

1. The Goal: The program's output states, "To pass this level, you need to suspend me and launch me again!". This means two copies of the program must be active in the same terminal.

2. The Tool: The challenge introduces the ctrl-z hotkey, which pauses the currently running program and returns you to the shell.

3. The Process:
 - First, the program is launched.
 - While it is running, the ctrl-z hotkey is pressed. The terminal shows ^Z and a "Stopped" message, and then gives us a new command line.
 - With the first copy suspended in the background, the program is launched a second time.

4. The Result: When the second copy runs, it checks for other running processes and finds the first suspended copy. It then says, "Yay, I found another version of me! Here is the flag:" and prints the flag.

```bash
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         138     129  0 17:35 pts/0    00:00:00 bash /challenge/run
root         140     138  0 17:35 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         138     129  0 17:35 pts/0    00:00:00 bash /challenge/run
root         145     129  0 17:35 pts/0    00:00:00 bash /challenge/run
root         147     145  0 17:35 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{UDX0QhixyJQ2VFFj8CRYgFluf6T.QX1QDO0wSN0AzNzEzW}
```
    
### New Learnings
1. The ctrl-z Hotkey: The main lesson is using ctrl-z to suspend a running process, pausing it and sending it to the background.

2. Suspended Vs Terminated: A suspended process is not terminated; it is paused and can be resumed later.

### References 
None