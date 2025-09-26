# pwn.college_garvit
# Hello Hackers

# Command History
The challenge introduces the concept of command history in Linux shells. Every command entered into the terminal is automatically saved, allowing users to quickly recall and reuse them with the up/down arrow keys. This exercise demonstrates how the history feature can make working with commands more efficient.

### Solve
**Flag:** `pwn.college{0Efq54Mttd329QM4X6nDfJCFH28.QX3YjM1wSN0AzNzEzW}`

To solve the challenge, I opened the terminal in the pwn.college DOJO. The flag had already been injected into my command history by the challenge setup. By pressing the up arrow key, I was able to scroll through the history until I found the command containing the flag. Executing it revealed the flag successfully.

```bash
hacker@hello~command-history:~$(up key pressed) the flag is pwn.college{EndsaGJNUNtWfD7EcmK0NtKYM0s.0lNzEzNxwSN0AzNzEzW}
```
    
### New Learnings
I learned about the command history feature in Linux shells:

1. Every command typed in the terminal is stored in a history buffer.
2. Pressing the up/down arrow keys lets you scroll through past commands.
3. The history feature makes it faster to re-run commands without retyping them.
4. Challenges can preload commands into the history, making retrieval easier.

### References 
None