# pwn.college_garvit
# File GLobbing

# Multiple Globs
This challenge introduces the use of multiple glob characters within a single argument to create flexible search patterns. The task is to navigate to the /challenge/files directory and execute a verification script. This script must be passed a single argument that is three characters or less, contains two * globs, and matches every file in the directory that contains the letter "p".

### Solve
**Flag:** `pwn.college{krHw_DxbzcY0-AIl-xWFhchNDUw.QXzIDO0wSN0AzNzEzW}`

The solution requires creating a generic pattern to find a specific character anywhere within a filename while adhering to the length and glob constraints.
1. Formulate the Glob Pattern: To find a file containing the letter "p" regardless of its position, the pattern *p* is used.
 - The first * matches any sequence of characters (or no characters) before the "p".
 - The p matches the literal character "p".
 - The second * matches any sequence of characters (or no characters) after the "p".
This pattern is exactly three characters long and uses two globs, satisfying all the challenge's constraints.

2. Execute the Commands: First, change into the correct directory. Then, run the verification script with the constructed glob pattern.

```bash
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
pwn.college{4s5Bb0ROccDltrTgeVBZ1A57I36.0lM3kjNxwSN0AzNzEzW}
```
    
### New Learnings
1. Combining Globs: The core lesson is that multiple wildcards can be used in a single argument to create powerful and flexible matching rules.

2. The Substring Match Pattern (*keyword*): The *p* pattern is a common and powerful idiom used on the command line to match any file that contains a specific substring anywhere in its name.

3. Zero-Length Matches: This challenge demonstrates that the * glob can match an empty string of characters. This is why *p* can successfully match filenames where "p" is the first or last character.

### References 
None