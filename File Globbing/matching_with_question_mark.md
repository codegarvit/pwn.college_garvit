# pwn.college_garvit
# File GLobbing

# Matching With ?
This challenge introduces the asterisk (*) character, a shell feature known as a "glob" or "wildcard." The * can be used in a path to match any sequence of characters. The task is to navigate to the /challenge directory using the cd command. However, the argument passed to cd must be four characters or less and must utilize the * glob.

### Solve
**Flag:** `pwn.college{AiO68ChQzwyKd5zWpgmIVrCFzQH.QXxIDO0wSN0AzNzEzW}`

The solution requires finding a short pattern containing the * wildcard that the shell will uniquely expand to the target path /challenge.

1. Formulate the Glob Pattern: A simple and effective pattern to match /challenge is /c*. This pattern is only three characters long, satisfying the length constraint.

2. Change Directory: When the command cd /c* is executed, the shell first performs glob expansion. It looks in the root directory (/) for all files or directories that start with the letter "c". In the context of the challenge, /challenge is the only match, so the shell replaces /c* with /challenge before the cd command runs.

3. Get the Flag: After successfully changing into the /challenge directory, the verification script is run to get the flag.

```bash
hacker@globbing~matching-with-:~$ cd /c*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{AiO68ChQzwyKd5zWpgmIVrCFzQH.QXxIDO0wSN0AzNzEzW}
hacker@globbing~matching-with-:/challenge$
```
    
### New Learnings
1. The * Glob: The primary lesson is that the * character acts as a wildcard in the shell, matching any sequence of characters (except for a leading dot). It is a fundamental tool for working with multiple files.

2. Shell Expansion: This challenge is a clear demonstration of shell expansion. The shell interprets special characters like * and replaces them with matching filenames before the actual command (cd) is executed.

### References 
None