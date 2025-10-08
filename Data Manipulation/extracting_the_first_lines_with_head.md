# pwn.college_garvit
# Data Manipulation

# Extracting The First Lines With Head
This challenge introduces the head command, which is used to grab just the early output of a program. The task is to create a "long composite command" that pipes the output of /challenge/pwn through head to get just the first 7 lines, and then pipes those lines onward to /challenge/college to get the flag.

### Solve
**Flag:** `pwn.college{cMX6AT3fdXd-foRj1g77lC283wR.0lNxEzNxwSN0AzNzEzW}`

The solution requires building a pipeline of three commands connected by two pipes to filter the data stream correctly.

1. The Goal: The /challenge/pwn program "outputs a bunch of data," but the /challenge/college program only wants the first 7 lines of that data. A filter is needed in the middle of the pipe.

2. The Tool: The challenge introduces the head command, which outputs the first few lines of its input. The -n option is used to specify exactly how many lines to output. For this challenge, head -n 7 is needed.

3. Command Construction: The pipeline is built in three stages:
 - The /challenge/pwn command is run to produce the initial data.
 - The pipe (|) sends this data to the head -n 7 command, which filters it, keeping only the first 7 lines.
 - A second pipe (|) sends the filtered 7-line output from head to the /challenge/college command.

```bash
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{cMX6AT3fdXd-foRj1g77lC283wR.0lNxEzNxwSN0AzNzEzW}
```
    
### New Learnings
1. The head Command: The primary lesson is the head command, which is "used to display the first few lines of its input". The -n option allows you to control how many lines are shown.

2. Filtering Data Streams: head is a simple type of filter. This challenge shows how you can place filters in the middle of a pipeline to modify a stream of data as it flows between commands.

### References 
None