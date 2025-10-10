# pwn.college_garvit
# Processes and Jobs

# Starting Background Processes
This challenge teaches how to "start them backgrounded right off the bat" without needing to suspend a process first. The method is to "append a & to the command".

### Solve
**Flag:** `pwn.college{krHw_DxbzcY0-AIl-xWFhchNDUw.QXzIDO0wSN0AzNzEzW}`

The solution requires running the challenge program with the ampersand (&) character at the end of the command.

1. The Goal: The challenge is to "Launch /challenge/run backgrounded".

2. The Tool: The challenge introduces the & operator, which tells the shell to run a command in the background immediately.

3. The Final Command: The program /challenge/run is executed with an appended &.
4. The Result: The shell starts the process in the background, gives you your command line back, and the program prints the flag.

```bash
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 165
hacker@processes~starting-backgrounded-processes:~$


Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{M4zasNKlJCS-M-3TObXUszwmtLw.QX5QDO0wSN0AzNzEzW} 
```
    
### New Learnings
1. The & Operator: The main lesson is that you can append a & to the command to immediately launch it in the background. 

2. Active Background Processes: This method results in a process that is "actively running, not suspended," in the background.
### References 
None