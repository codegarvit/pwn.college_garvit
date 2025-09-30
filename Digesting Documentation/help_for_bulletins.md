# pwn.college_garvit
# Digesting Documentation

# Help For Bulletins
This challenge introduces the help command, which is a shell builtin used to get documentation for other shell builtins (like cd or echo). The task is to use help to learn how to use this level's challenge command—which is a builtin—and provide it with the correct "secret value" to get the flag.

### Solve
**Flag:** `pwn.college{4BDRWBpyp8kqW5PTa3SkfOKGSzY.QX0ITO0wSN0AzNzEzW}`
The solution requires a direct application of the information found in the challenge builtin's help menu.

1. Getting Help: The first step is to run the help command on the challenge builtin to see its usage instructions.

2. Finding the Secret: The output of the help command explicitly provides the entire solution. It shows that a --secret VALUE option is available and then states what the correct value is:
You must be sure to provide the right value to --secret. That value is "AsjoyXC2".

3. Executing the Command: The final step is to run the challenge command with the option and the exact value specified in the help text.
This command correctly provides the secret argument, and the program responds by printing the flag: pwn.college{AsJoyXC2AF41GsmDu81s507sVbt.QX0ETO0wSN0AzNzEzW}.

```bash
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "AsJoyXC2".
hacker@man~help-for-builtins:~$ challenge --secret AsJoyXC2
Correct! Here is your flag!
pwn.college{AsJoyXC2AF41GsmDu81s5O7sVbt.QX0ETO0wSN0AzNzEzW}

```
    
### New Learnings
1. The help Command: The primary lesson is the use of the help <builtin_name> command to get documentation for commands that are built directly into the shell.

2. Builtins vs. External Programs: This challenge reinforces the distinction between external programs (which often have man pages) and shell builtins (which are documented via help).

### References 
None