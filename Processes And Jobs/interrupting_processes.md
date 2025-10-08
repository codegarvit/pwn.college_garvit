# pwn.college_garvit
# Processes and Jobs

# Interrupting Processes
This challenge teaches how to use the ctrl-c hotkey to get rid of the process that's clogging up your terminal. The task is to run the /challenge/run program, which will refuse to give you the flag until you interrupt it.

### Solve
**Flag:** `pwn.college{gn2Qjez9oNyaDBgEiHMdHve9Kao.QXzQDO0wSN0AzNzEzW}`
The solution requires running the program and then using the keyboard hotkey to send the interrupt signal.

1. The Goal: The challenge is designed so that the /challenge/run program must be "interrupted" in order to give you the flag.

2. The Process: The solution is an interactive, two-step process:
 - First, the /challenge/run program is started in the terminal.
 - Second, while the program is running, the ctrl-c hotkey is pressed (holding down the Ctrl key and pressing c). This sends the interrupt signal.

3. The Result: Upon receiving the interrupt, the program is designed to print the flag before it exits.

```bash
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{gn2Qjez9oNyaDBgEiHMdHve9Kao.QXzQDO0wSN0AzNzEzW}
```
    
### New Learnings
1. The ctrl-c Hotkey: The main lesson is using the ctrl-c hotkey to send an 'interrupt' signal to the application currently running in the foreground of your terminal.

2. Process Interruption: This challenge shows that an "interrupt" doesn't always just kill a program. A program can be written to catch the interrupt and perform a specific action (like printing a flag) before it exits.
### References 
None