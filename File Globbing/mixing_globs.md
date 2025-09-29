# pwn.college_garvit
# File GLobbing

# Mixing Globs
This challenge requires combining different types of globs ([] and *) to create a specific file-matching pattern. The task is to navigate to the /challenge/files directory and execute a verification script, /challenge/run. This script must be passed a single argument: a glob pattern of 6 characters or less that expands to match exactly three files: "challenging", "educational", and "pwning".

### Solve
**Flag:** `pwn.college{0SYpRweekIHXV-NvsQdz21_7D55.QX1IDO0wSN0AzNzEzW}`

The solution lies in creating a pattern that is both short and specific enough to match only the three target files.
1. Analyze the Target Filenames: The target files are challenging, educational, and pwning. A key observation is that their first letters (c, e, p) are unique among the other files in the directory.

2. Construct the Glob Pattern: A pattern can be built based on this observation:
The character set glob [cep] is used to match any file starting with 'c', 'e', or 'p'.
The wildcard glob * is used to match the rest of each filename.
The combined pattern is [cep]*. This pattern is exactly 6 characters long and correctly identifies the three target files.

3. Execute the Commands: First, change into the correct directory. Then, run the verification script with the unquoted glob pattern, allowing the shell to expand it into the three required filenames.

```bash
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ ls
amazing    challenging  educational  great  incredible  kind      magical  optimistic  queenly  splendid   uplifting   wonderful  youthful
beautiful  delightful   fantastic    happy  jovial      laughing  nice     pwning      radiant  thrilling  victorious  xenial     zesty
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{0SYpRweekIHXV-NvsQdz21_7D55.QX1IDO0wSN0AzNzEzW}
```
    
### New Learnings
1. Combining Glob Types: The core lesson is how to mix different glob types, like character sets [] and wildcards *, to create more precise and powerful matching patterns than either can alone.

2. Analytical Pattern Matching: The challenge encourages a more analytical approach to creating patterns. Instead of using generic wildcards, you must analyze the set of target files to find the shortest, most efficient pattern that includes all targets while excluding all others.

### References 
None