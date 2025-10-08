# pwn.college_garvit
# Processes and Jobs

# Killing Processes
This challenge teaches how to "terminate" processes using the kill command. The task is to solve a situation where one program, /challenge/run, refuses to work while another process, dont_run, is running. You must first find the dont_run process and then kill it to get the flag.

### Solve
**Flag:** `pwn.college{AzxqHAC-WG6FaP8hwkLRYb4rV9Z.QXyQDO0wSN0AzNzEzW}`

The solution requires a sequence of commands to find the Process ID (PID) of the target process, terminate it, and then run the main challenge program.

1. The Goal: The challenge is to "get rid of" the dont_run process so that /challenge/run can be executed successfully.

2. The Tools: The challenge shows that you can find a process with ps and grep, and terminate it with the kill command, which takes a PID as an argument.

3. Finding the PID: The ps command is piped to grep to find the dont_run process and its process identifier.
The output shows the process /challenge/dont_run with a PID of 136.

4. Terminating the Process: The kill command is then used with the PID that was found.

5. Getting the Flag: With the dont_run process terminated, /challenge/run is executed to get the flag.

```bash
hacker@processes~killing-processes:~$ ps aux | grep dont_run
hacker       136  0.0  0.0 231576  3520 ?        Ss   17:30   0:00 /challenge/dont_run
hacker       155  0.0  0.0 230696  2560 pts/0    S+   17:32   0:00 grep --color=auto dont_run
hacker@processes~killing-processes:~$ kill 136
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{AzxqHAC-WG6FaP8hwkLRYb4rV9Z.QXyQDO0wSN0AzNzEzW}
```
    
### New Learnings
1. The kill command: The main lesson is using kill <PID> to "terminate a process".

2. Finding a PID: This challenge teaches how to use ps and grep together to find a specific running process and get its PID.

### References 
None