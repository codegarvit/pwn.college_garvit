# pwn.college_garvit
# Praciting Piping

# Filtering With Grep -v
This challenge introduces the -v (invert match) option for the grep command, which shows lines that do not match a pattern. The task is to filter the output of a program that produces over a thousand decoy flags alongside the one real flag. The decoy flags are identifiable because they all contain the word "DECOY".

### Solve
**Flag:** `pwn.college{AxaZOXasPEWq2HAI5sUQBquy38C.0FOxEzNxwSN0AzNzEzW}`
The solution requires piping the program's output to grep and using the -v option to exclude the decoy flags. Instead of trying to find the one line that is the real flag, the logic is inverted: we remove all the lines that we know are decoys.

1. The Data Stream: The /challenge/run command is executed on the left side of a pipe. It produces a stream of text containing both the real flag and many decoy flags.

2. The Filter: The grep command is placed on the right side of the pipe. The -v option is used to invert its behavior. It is given the pattern DECOY, instructing it to discard any line that contains this word.

3. The Command: The complete command pipes the output of the program directly to the inverted grep filter.

```bash
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{AxaZOXasPEWq2HAI5sUQBquy38C.0FOxEzNxwSN0AzNzEzW}
```
    
### New Learnings
1. The grep -v Option: The primary lesson is the function of the -v option, which transforms grep from a tool for finding matching lines into a powerful tool for removing them.

2. Exclusionary Filtering: This challenge demonstrates a common data processing strategy. Sometimes, it's easier to define a pattern for the data you don't want and filter it out, rather than trying to define a pattern for the specific data you do want.

### References 
None