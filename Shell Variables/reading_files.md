# pwn.college_garvit
# Shell Variables

# Reading Files
This challenge teaches an efficient, shell-native method for reading the contents of a file directly into a variable. It contrasts the common but less efficient "Useless Use of Cat" (VAR=$(cat file)) with the more direct approach of combining the read command with input redirection (<). The task is to read the content of the file /challenge/read_me into a variable named PWN in a single command.

### Solve
**Flag:** `pwn.college{ceeZqJronxga0fMN65jsHV99vUN.QXwIDO0wSN0AzNzEzW}`
The solution requires combining two previously learned concepts: the read command and input redirection.

1. The Goal: The challenge is to capture the contents of the /challenge/read_me file into the PWN variable.

2. The Technique: The prompt demonstrates that you can redirect a file into the standard input of the read command. This causes read to get its data from the file instead of from the keyboard.

3. Command Construction:
 - The read PWN command tells the shell to read from standard input and store the result in the PWN variable.
 - The < /challenge/read_me operator redirects the contents of the specified file to the standard input of the read command.

4. The Final Command: Combining these parts gives the single, efficient command to solve the challenge.

```bash
hacker@variables~reading-files:~$ read PWN < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{ceeZqJronxga0fMN65jsHV99vUN.QXwIDO0wSN0AzNzEzW}
```
    
### New Learnings
1. Efficient File Reading: The main lesson is the read VAR < file idiom. It is a highly efficient, shell-native method for storing a file's contents in a variable without needing to start a separate cat process.

2. "Useless Use of Cat": The challenge introduces this common term for unnecessarily using the cat command. Learning to avoid it by using shell-native redirection is a step towards more advanced shell scripting.

3. Combining read and Redirection: This exercise shows the flexibility of the read command. While it's often used for interactive input from the keyboard, it can be seamlessly repurposed to read from files by redirecting its standard input.

### References 
None