# pwn.college_garvit
# Digesting Documentation

# Helpful Programs
This challenge focuses on a common way to learn about a program's functionality when it doesn't have a manual page: using the built-in help argument. Most command-line tools will print their own documentation if run with a special argument like --help or -h. The task is to use this feature on the /challenge/challenge program to discover how to make it print the flag.

### Solve
**Flag:** `pwn.college{QI_59VjL6-Y_Bv1L8vRCUNkO6o0.QX3IDO0wSN0AzNzEzW}`

The solution is a two-step process discovered by reading the program's own help message.

1. Get Help: First, run the program with the --help argument to display its usage and options.

2. Analyze the Output: The help message reveals a clever, two-part mechanism:
The -g option will "get the flag, if given the correct value."
The -p option will "print the value that will cause the -g option to give you the flag."

3. Find the Secret Value: Following the instructions, run the program with the -p option to get the secret value.

4. Get the Flag: Finally, run the program with the -g option, providing the secret value you just found.

```bash
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 596
hacker@man~helpful-programs:~$ /challenge/challenge -g 596
Correct usage! Your flag: pwn.college{QI_59VjL6-Y_Bv1L8vRCUNkO6o0.QX3IDO0wSN0AzNzEzW}
```
    
### New Learnings

1. The --help Convention: The primary lesson is that --help (and its common shorthand -h) is a standard, widely-used argument for getting usage information from command-line programs. It should be one of the first things you try when encountering a new command.

2. Reading Usage Information: This challenge provides practice in interpreting the usage: line and the list of optional arguments that help messages typically provide.

### References 
None