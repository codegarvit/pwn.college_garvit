# pwn.college_garvit
# Processes and Jobs

# Foregrounding Processes
This challenge teaches how to take a backgrounded process and foreground it using the fg command. The task is to launch the challenge program, suspend it, resume it in the background, and then finally bring it back to the foreground to get the flag.

### Solve
**Flag:** `pwn.college{oZSNDeiCZN82a8kqIeTECv1ZUpA.QX4QDO0wSN0AzNzEzW}`

1. The Goal: The program's instructions state, "To pass this level, you need to suspend me, resume the suspended process in the background, and then foreground it".

2. The Process:
 - First, the program is launched.
 - Second, the Ctrl-Z hotkey is pressed to "suspend" the process. The terminal shows ^Z and a "Stopped" message.
 - Third, the bg command is used to resume the process so it is running the background.
 - Finally, the fg command is used to resume into the foreground.

3. The Result: When the process is brought back to the foreground, it prints "YES! Great job! I'm now running in the foreground," followed by the flag.

```bash
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.
fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{oZSNDeiCZN82a8kqIeTECv1ZUpA.QX4QDO0wSN0AzNzEzW}
hacker@processes~foregrounding-processes:~$ client_loop: send disconnect: Broken pipe
```
    
### New Learnings
1. The fg Command: The main lesson is that the fg command can be used to bring a process that is "running the background" back into the "foreground," giving you control of it again.

### References 
None