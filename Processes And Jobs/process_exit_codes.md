# pwn.college_garvit
# Processes and Jobs

# Process Exit Codes
This challenge teaches how to "list running processes" using the ps command. For this challenge, a program has been "renamed /challenge/run to a random filename" and has already been "launched," so you must find it in the "running process list" to get the flag.

### Solve
**Flag:** `pwn.college{krHw_DxbzcY0-AIl-xWFhchNDUw.QXzIDO0wSN0AzNzEzW}`

The solution requires using ps to find the full path of the hidden running process and then running that path to get the flag.

1. The Goal: The challenge is to find a program that is already running but has a random name, so it can't be found with ls. The only way to find it is to look at the list of all running processes.

2. The Tool: The ps command with arguments like aux is used to list processes for "all users" in a "user-readable" format. To prevent the output from being cut short, the ww option can be added to make ps auxww.

3. Finding the Process: To find the running program, you run the ps command and look through the COMMAND column for a process located in the /challenge/ directory.
The output shows the randomly named process: /challenge/2780-run-30570.

4. To finish the challenge, we launch the program by running the full path that we discovered.


```bash
hacker@processes~listing-processes:~$ /challenge/2780-run-30570
Yahaha, you found me! Here is your flag:
pwn.college{09hxr3aCnMTWKoQ-pptsTjTwmjZ.QX4MDO0wSN0AzNzEzW}
Now I will sleep for a while (so that you could find me with 'ps').
```
    
### New Learnings
1. The ps command: The main lesson is using ps aux or ps -ef to see a detailed list of all processes currently running on the system.

2. Process Information: The output of ps provides useful information about each process, like its PID (Process ID) and the full COMMAND used to start it.

3. Finding Running Programs: This challenge shows how ps is a powerful tool for finding and identifying running programs, even when you don't know their name or exact location.

### References 
None