# pwn.college_garvit
# File GLobbing

# Matching Paths With []
This challenge expands on the concept of globbing by demonstrating that wildcards can be used within entire paths, not just on filenames in the current directory. The task is to execute the /challenge/run script from the home directory. The script must be passed a single argument: a glob pattern using [] that expands into the absolute paths of four specific files (file_a, file_b, file_s, and file_h) located in /challenge/files.

### Solve
**Flag:** `pwn.college{UGl-d94BxIEdAIOwgeyGZdmGuM1.QX0IDO0wSN0AzNzEzW}

The solution requires constructing a single glob pattern that includes the full absolute path to the target files.
1. Identify the Path Prefix: The target files are all located in /challenge/files and share the common prefix file_. Therefore, the absolute path prefix for all of them is /challenge/files/file_.

2. Construct the Glob: The final character of each target filename is one of b, a, s, or h. This set of characters can be matched with the glob [bash].

3. Combine and Execute: The absolute path prefix is combined with the character set glob to form a single argument. This argument is then passed to the verification script.



```bash
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{UGl-d94BxIEdAIOwgeyGZdmGuM1.QX0IDO0wSN0AzNzEzW}
```
    
### New Learnings
1. Globbing on Full Paths: The primary lesson is that shell globbing works on any part of a path string. You can use wildcards to match directory names or filenames in any location, whether specified by an absolute or relative path.

2. Precision with Absolute Paths: The challenge reinforces the importance of using precise, absolute paths to ensure commands work predictably, regardless of your current working directory.

3. Shell Expansion vs. Program Arguments: This exercise clearly demonstrates the shell's order of operations. The user types a single argument (/challenge/files/file_[bash]), but the shell processes the wildcards and expands it into multiple arguments before the challenge program ever sees them.

### References 
None