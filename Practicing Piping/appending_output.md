# pwn.college_garvit
# File GLobbing

# Appending Output
This challenge introduces the concept of appending output to a file using the >> operator. Unlike the > operator which overwrites a file's contents, >> adds the new output to the end of the file. The task involves a program, /challenge/run, that needs to be executed twice. The first execution writes the first half of the flag to a file, and the second execution outputs the second half. To get the complete flag, the output of the second run must be correctly appended to the first.



### Solve
**Flag:** `pwn.college{khluq5gb70q01s0VlgqCJLyfwcP.QX3ATO0wSN0AzNzEzW}`
The solution requires a specific sequence of commands to correctly assemble the two halves of the flag in a single file.

1. Write the First Half: The /challenge/run program is executed for the first time. Its output is redirected using the > operator to create the file /home/hacker/the-flag and write the first part of the flag into it.

2. Append the Second Half: The program is run a second time. This time, the append operator >> must be used to add the second half of the flag to the end of the file without erasing the first half.


3. Read the Complete Flag: With both halves now in the file, the cat command is used to display the contents of /home/hacker/the-flag, revealing the complete flag.

```bash
hacker@piping~appending-output:~$ /challenge/run > /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 |
\|/ This is the first half:
 v
pwn.college{khluq5gb70q01s0VlgqCJLyfwcP.QX3ATO0wSN0AzNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>)
rather than *append* mode (>>), and so the write of the second half to stdout
overwrote the initial write of the first half directly to the file. Try append
mode!
```
    
### New Learnings
1. The >> Append Operator: The primary lesson is the use of the >> operator to add a command's output to the end of an existing file without deleting its current contents. This is essential for tasks like creating log files or aggregating data.

2. Truncation (>) vs. Appending (>>): This challenge directly contrasts the behavior of the two main output redirection operators. Using > will truncate (overwrite) the file, while >> will append to it. Choosing the correct one is crucial to avoid accidental data loss.

### References 
None