# pwn.college_garvit
# Comprehending Commands

# Cat:  Not the Pet,but the Command!
There are two files: /challenge/decoys_only.txt (containing 100 fake flags) and /challenge/decoys_and_real.txt (containing the same 100 fake flags plus one real flag). The task is to find the single line that is different between these two files to isolate the real flag.

### Solve
**Flag:** `pwn.college{whe9mmdOtIobpct73WgOicvJLMP.01MwMDOxwSN0AzNzEzW}`

The goal is to find the single unique line in decoys_and_real.txt. Manually comparing two files with over 100 lines each is tedious and prone to error.

The Linux command line has a specialized tool for this exact task: diff. The diff command compares two files and outputs only the lines that differ.

The syntax is straightforward: diff <file1> <file2>.

By running diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt, you instruct the system to perform a line-by-line comparison. It will ignore all the common lines (the 100 decoys) and print out only the line that exists in the second file but not the first. This unique line is the flag.
```bash
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
2a3
> pwn.college{whe9mmdOtIobpct73WgOicvJLMP.01MwMDOxwSN0AzNzEzW}
```
    
### New Learnings
The diff command is used to compare two files and show the lines that are different.

It's an invaluable tool for programmers to track changes in code or for anyone needing to find discrepancies between text files.

### References 
None