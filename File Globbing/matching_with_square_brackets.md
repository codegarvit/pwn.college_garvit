# pwn.college_garvit
# File GLobbing

# Matching With []
This challenge introduces globbing with square brackets ([]), which is used to match any single character from a specified set. The task is to navigate to the /challenge/files directory and then execute the /challenge/run script. This script requires a single argument: a glob pattern using [] that expands to match exactly four files: file_b, file_a, file_s, and file_h.

### Solve
**Flag:** `pwn.college{krHw_DxbzcY0-AIl-xWFhchNDUw.QXzIDO0wSN0AzNzEzW}`

The solution requires creating a precise glob pattern that matches only the target files.
1. Analyze the Target Filenames: The files to be matched all share a common prefix, file_. The only difference is the final character, which is one of b, a, s, or h.

2. Construct the Glob Pattern: The square bracket [] syntax is perfect for this situation. By placing the desired characters inside the brackets, we create a pattern that will match any one of them. The resulting pattern is file_[bash].

3. Execute the Commands: The first step is to change into the correct directory. The second is to run the verification script with the constructed glob pattern.



```bash
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
You got it! Here is your flag!
pwn.college{krHw_DxbzcY0-AIl-xWFhchNDUw.QXzIDO0wSN0AzNzEzW}
```
    
### New Learnings
1. Character Set Globbing []: The core lesson is the use of square brackets [] to match a single character from a specific list. This allows for more granular control than the ? (any single character) or * (any sequence of characters) globs.

2. Shell Expansion: This challenge reinforces that the shell processes glob patterns before executing the command. It sees the pattern file_[bash], finds all matching files, and substitutes their names into the command line as separate arguments.

3. Combining Literals and Globs: The solution demonstrates how to combine literal text (file_) with glob patterns ([bash]) to create a specific and powerful file-matching rule.

### References 
None