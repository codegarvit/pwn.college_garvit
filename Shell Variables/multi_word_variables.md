# pwn.college_garvit
# Shell Variables

# Multi Word Variables
This challenge teaches how to assign a value that contains spaces to a shell variable. Because the shell uses spaces to separate parts of a command, a multi-word value must be enclosed in quotes to be treated as a single string. The task is to set the variable PWN to the value COLLEGE YEAH.

### Solve
**Flag:** `pwn.college{wCBE7ds4V_7IRMAsb1wpYAhq-T9.QXwYTN0wSN0AzNzEzW}`
The solution requires using quotes to ensure the shell correctly interprets the multi-word value as a single piece of data.

The core problem is that the shell interprets spaces as separators. A command like PWN=COLLEGE YEAH would be seen as an instruction to set PWN to COLLEGE and then run a separate command called YEAH, which would fail.

To solve this, the value must be quoted. The challenge demonstrates using double quotes (" ") to group the words into a single token. The final command is constructed by taking the variable name, the equals sign, and the correctly quoted multi-word string.
```bash
hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{wCBE7ds4V_7IRMAsb1wpYAhq-T9.QXwYTN0wSN0AzNzEzW}
```
This command correctly assigns the single string "COLLEGE YEAH" to the PWN variable, which satisfies the challenge's condition.
    
### New Learnings
1. The Role of Quotes: The main lesson is that quotes (either single ' ' or double " ") are used to group strings. This prevents the shell from splitting a value into multiple arguments at the spaces.

2. Shell Tokenization: This is a practical example of how the shell tokenizes, or breaks down, a command line. Quoting is the primary way to control this process and ensure data with spaces is handled correctly.

3. Storing Multi-word Strings: We frequently need to store file paths, user input, or messages that contain spaces. 

### References 
None