# pwn.college_garvit
# Data Manipulation

# Extracting Specific Sections of Text
This challenge introduces the cut command, which is used to "grab specific columns of data" from its input. The task is to use cut to extract the column containing the flag characters from the output of the /challenge/run program, and then use tr to join those characters into a single line.

### Solve
**Flag:** `pwn.college{YPjdSPaSoMzkVJ96n9GXinX8Y2u.01NxEzNxwSN0AzNzEzW}`

The solution requires building a three-stage pipeline to run the program, extract the correct data, and format the final output.

1. Investigation: First, by running /challenge/run alone, one can see that its output has columns separated by a "space character" and that the flag characters are in the second column.

2. The Tools: The challenge requires using the cut command. The -d argument specifies the "column delimiter," and the -f argument specifies which "field" (column) to extract. The challenge also mentions piping the result to tr -d '\n' to "join them together into a single line".

3. Command Construction: The pipeline is built as follows:
 - The /challenge/run command produces the lines of data.
 - Its output is piped (|) to cut -d " " -f 2, which extracts only the second column.
 - The output of cut (a single column of characters) is then piped (|) to tr -d '\n' to remove the newlines.

```bash
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d '\n'
pwn.college{YPjdSPaSoMzkVJ96n9GXinX8Y2u.01NxEzNxwSN0AzNzEzW}
```
    
### New Learnings
1. The cut Command: The main lesson is using the cut command with the -d (delimiter) and -f (field) arguments to "extract specific columns" from text data.

### References 
None