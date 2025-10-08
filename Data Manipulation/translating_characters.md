# pwn.college_garvit
# Data Manipulation

# Translating Characters
This challenge introduces the tr (translate) command, a utility that modifies a stream of text by replacing or deleting characters. The task is to fix the output of the /challenge/run program, which prints the flag but with the case of every letter swapped (e.g., 'A' becomes 'a' and 'b' becomes 'B').

### Solve
**Flag:** `pwn.college{Ml-YMhOz3GNb9LCftBo2WRMRtW6.01MxEzNxwSN0AzNzEzW}`

The solution requires piping the output of the challenge program into a correctly configured tr command that will reverse the case-swapping transformation.
1. The Problem: The output of /challenge/run is a case-inverted version of the flag. A tool is needed to swap the case of every letter back to normal.

2. The Tool: The tr command is perfect for this. It takes two sets of characters as arguments, tr SET1 SET2, and replaces each character from SET1 with the character at the same position in SET2.

3. Command Construction:
 - The 'a-zA-Z' character set is used as the first argument. This represents all lowercase letters followed by all uppercase letters.

 - The 'A-Za-z' character set is used as the second argument. This represents all uppercase letters followed by all lowercase letters.

 - tr will map the first character of set 1 ('a') to the first of set 2 ('A'), the second to the second ('b' to 'B'), and so on. This creates a perfect case-swapping effect.

```bash
hacker@data~translating-characters:~$ /challenge/run | tr 'a-zA-Z' 'A-Za-z'
yOUR CASE-SWAPPED FLAG:
pwn.college{Ml-YMhOz3GNb9LCftBo2WRMRtW6.01MxEzNxwSN0AzNzEzW}
```
    
### New Learnings
1. The tr Command: The main lesson is the use of the tr command for character-by-character translation. It's a standard and efficient tool for simple text transformations like changing case, deleting characters, or replacing one set of characters with another.

2. Character Sets/Ranges: This challenge demonstrates the use of character ranges (e.g., a-z) to define large sets of characters concisely.

### References 
None