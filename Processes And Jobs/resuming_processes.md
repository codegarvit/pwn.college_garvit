# pwn.college_garvit
# Processes and Jobs

# Resuming Processes
This challenge teaches how to resume a suspended process using the fg command, a shell builtin that takes a suspended process and puts it back in the foreground of your terminal. 

### Solve
**Flag:** `pwn.college{gbDS8DUayxgMFYa_hlc42mqKt5r.QX2QDO0wSN0AzNzEzW}`

1. The Goal: The challenge requires a specific sequence of actions: the /challenge/run program must first be suspended and then resumed.

2. The Tools: This process uses two shell features working together:
 - The ctrl-z hotkey is used to "suspend" the running process.
 - The fg command is used to "resume" it.

3. The Process:
 - First, the program is launched in the terminal.
 - While it is running, the ctrl-z hotkey is pressed. This pauses the process and puts it in the background.
 - Finally, the fg command is run. This brings the suspended process back to the foreground and resumes its execution.

```bash
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{gbDS8DUayxgMFYa_hlc42mqKt5r.QX2QDO0wSN0AzNzEzW}
Don't forget to press Enter to quit me!
```
    
### New Learnings
1. The fg Command: The main lesson is the use of the fg command to take a suspended process, resume it, and put it back in the foreground of your terminal.

2. Foreground Processes: A process in the foreground is the one that is currently active and can receive input from your keyboard. The fg command is used to select which suspended process becomes the active one.

### References 
None