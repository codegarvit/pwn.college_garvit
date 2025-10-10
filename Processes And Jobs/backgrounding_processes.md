# pwn.college_garvit
# Processes and Jobs

# Backgrounding Processes
This challenge teaches how to resume processes in the background using the bg command. This allows a process to keep running while giving you your shell back to run more commands. 

### Solve
**Flag:** `pwn.college{I-n1ypipc_vpxOPNtJnmfHpWlGn.QX3QDO0wSN0AzNzEzW}`

The solution requires following the specific sequence of actions laid out by the challenge itself: launch the program, suspend it, resume it in the background, and then launch it again.

1. The Goal: The program's output states, "To pass this level, you need to suspend me, resume the suspended process in the background, and then launch a new version of me!".

2. The Process: The solution is an interactive, four-step process:
 - First, the program is launched.
 - Second, while the program is running, the Ctrl-Z hotkey is pressed. The terminal shows ^Z and a "Stopped" message, and you get your command line back.
 - Third, the bg command is used to resume the "Stopped" process and keep it running in the background.
 - Fourth, with the first copy now running in the background, the program is launched a second time.

3. The Result: When the second copy runs, it checks the running processes and says, "Yay, I found another version of me running in the background! Here is the flag:" and prints the flag.


```bash
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         138 S+   bash /challenge/run
root         140 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.
/challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         138 S    bash /challenge/run
root         148 S    sleep 6h
root         149 S+   bash /challenge/run
root         151 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{I-n1ypipc_vpxOPNtJnmfHpWlGn.QX3QDO0wSN0AzNzEzW}
```
    
### New Learnings
1. The bg Command: The main lesson is using the bg command to take a stopped (suspended) process and resume it so it is running in the background.

2. Suspended vs Backgrounded: This challenge shows the difference between a suspended process (paused, shown with a T in the STAT column of ps) and a backgrounded process (actively running or sleeping, shown with an S or R).

3. Finding Running Programs: This challenge shows how ps is a powerful tool for finding and identifying running programs, even when you don't know their name or exact location.

### References 
None