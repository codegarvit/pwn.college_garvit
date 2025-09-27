# pwn.college_garvit
# Comprehending Commands

# Cat:  Not the Pet,but the Command!
The challenge illustrates the uses of the cat command.The primary purpose of cat is to read the contents of files and display them in the terminal.
It can also concatenate multiple files and show them sequentially, or even read from the terminal if no file is given.

### Solve
**Flag:** `pwn.college{goryZNX3x92aQFH0bPLstxZtNbH.QXxcTN0wSN0AzNzEzW}`

To solve this challenge, the task was to read the contents of a file called flag that was placed in the home directory. The cat command was used to display the file’s contents, successfully returning the flag.

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{goryZNX3x92aQFH0bPLstxZtNbH.QXxcTN0wSN0AzNzEzW}
```
    
### New Learnings

I learned the following concepts about the cat command in Linux:
1. Cat displays the contents of files directly in the terminal.
2. Multiple files can be provided as arguments, and their contents will be concatenated in order.
3. If no arguments are given, cat will read from the terminal input and output it.

### References 
None