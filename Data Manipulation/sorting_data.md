# pwn.college_garvit
# Data Manipulation

# Sorting Data
This challenge introduces the tr (translate) command, a utility that modifies a stream of text by replacing or deleting characters. The task is to fix the output of the /challenge/run program, which prints the flag but with the case of every letter swapped (e.g., 'A' becomes 'a' and 'b' becomes 'B').

### Solve
**Flag:** `pwn.college{YibM2E09K5HJwEQmt5Tjkq7yaTR.0FM0MDOxwSN0AzNzEzW}`

The solution relies on a key piece of information given in the challenge: when sorted alphabetically, "the real flag will be at the end".
1. The Goal: The challenge is to isolate the "real flag" from a file containing many "fake flags".
2. The Tool: The sort command is the specified tool, which by default "orders lines alphabetically".
3. The Final Command: The sort command is run with the /challenge/flags.txt file as its argument.
4. The Result: This command prints all 101 flags to the screen, but in sorted alphabetical order. Because the real flag is designed to appear last, you simply need to look at the very last line of the output to find your flag.


```bash
hacker@data~sorting-data:~$ sort /challenge/flags.txt
owm.bnklefe{YibM2E09J5GJwEPlt4Tjkp7yaTR.0EM0MDOwwSN0AyNzEzV}
owm.bolkege{YibL2E09J5HJvDPmt4Sjkp7xaTR.0FM0MDOxwSN0AyNyEyW}
......
.....
pwn.college{YibM2E09K5HJwEQmt5Tjkq7yaTR.0FM0MDOxwSN0AzNzEzW}
```
    
### New Learnings
1. The sort Command: The main lesson is how to use the sort command to "organize data." By default, it sorts lines alphabetically, which is a common need when working with text files.

2. Sorting Options: The challenge mentions several arguments that can change how sort works, such as -r (reverse order), -n (numeric sort), and -u (unique lines only).

### References 
None