# pwn.college_garvit
# File GLobbing

# Matching With ?
This challenge introduces the question mark (?) glob character, which serves as a single-character wildcard in the shell. The task is to navigate to the /challenge directory using the cd command with an argument that utilizes the ? glob. The challenge includes a hidden constraint that the command argument cannot contain the letters 'c' or 'l'.

### Solve
**Flag:** `pwn.college{AiO68ChQzwyKd5zWpgmIVrCFzQH.QXxIDO0wSN0AzNzEzW}`

The solution requires constructing a glob pattern that matches /challenge while adhering to all the rules, including the hidden ones.
1. Discover the Hidden Constraint: An initial, straightforward attempt like cd /?hallenge fails with an error message stating that the characters 'c' and 'l' are disallowed.

2. Formulate the Correct Pattern: To bypass this constraint, every forbidden character in the target path /challenge must be replaced with the ? wildcard.
c is replaced with ?
l is replaced with ?
l is replaced with ?
This results in the correct pattern: /?ha??enge.

3. Execute the Commands: The cd command is run with the new pattern. The shell successfully expands this to /challenge. The verification script is then run to obtain the flag.

```bash
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{Um-NU_WTTjuKyUVGLivRXX7Cxlo.QXyIDO0wSN0AzNzEzW}
```
    
### New Learnings
1. The ? Glob: The core lesson is the function of the ? wildcard, which matches any single character. This contrasts with the * wildcard, which matches any sequence of characters.

2. Adapting to Constraints: The challenge teaches the importance of adapting a solution based on new information. The hidden constraint forces a more creative and thorough application of the globbing concept.

### References 
None