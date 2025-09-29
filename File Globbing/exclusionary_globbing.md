# pwn.college_garvit
# File GLobbing

# Exclusionary Globbing
This challenge introduces exclusionary globbing, a feature of the shell that allows you to match files that do not contain certain characters. By placing a ! or ^ as the first character inside a bracket expression ([]), the pattern is inverted. The task is to navigate to the /challenge/files directory and run a verification script with a glob that selects all files except those starting with the letters 'p', 'w', or 'n'.

### Solve
**Flag:** `pwn.college{sQikFZIj8Fv8k0uIugEjcH4uZq0.QX2IDO0wSN0AzNzEzW}`

The solution requires building a glob pattern that uses the exclusionary syntax to filter the file list.
1. Identify the Exclusion Set: The characters to be excluded from the first position of the filename are p, w, and n.

2. Construct the Glob Pattern:
The set of excluded characters is placed inside brackets: [pwn].
A ! is added as the very first character inside the brackets to invert the match: [!pwn]. This now matches any single character that is not p, w, or n.
A * is appended to match the rest of any filename that passes the first character check.
The final pattern is [!pwn]*.

3. Execute the Commands: First, change into the correct directory. Then, run the verification script with the exclusionary glob pattern.


```bash
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{sQikFZIj8Fv8k0uIugEjcH4uZq0.QX2IDO0wSN0AzNzEzW}
```
    
### New Learnings
1. Exclusionary Globbing [!...]: The core lesson is that placing a ! (or ^) at the start of a character set inverts its meaning, matching any character not in the set. This is a powerful technique for filtering out files.

2. Combining Glob Logic: The solution, [!pwn]*, effectively combines two types of globbing: an exclusionary character set for the first character and a wildcard for the rest of the string. This demonstrates the composability of shell patterns.
### References 
None