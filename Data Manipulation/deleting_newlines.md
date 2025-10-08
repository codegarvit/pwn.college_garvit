# pwn.college_garvit
# Data Manipulation

# Deleting Newlines
This challenge shows how to remove a line separator, or newline, from a stream of data. The task is to use the tr command's -d flag and the escaped newline specification (\n) to delete a bunch of newlines that are injected into the flag.

### Solve
**Flag:** `pwn.college{MwLiuRkIiyyD8kSsfGfRfgYAITM.0VNxEzNxwSN0AzNzEzW}`

The solution requires combining the challenge program with the tr command to filter out the unwanted newline characters.
The challenge is that the /challenge/run program will print the flag, but with many newlines added in, making it hard to read. To get the clean flag, this stream of data must be modified.

1. The Tool: The challenge teaches that tr can delete characters using the -d flag. It also shows that a newline character can be specified by escaping it as \n, and that this must be in quotes.

2. Command Construction: A pipeline is created.
 - The /challenge/run command is executed to produce the output.
 - The pipe (|) sends this output to the tr command.
 - The tr -d '\n' command receives the stream of data. The -d flag tells tr to delete characters, and the argument '\n' specifies that the character to delete is the newline.

```bash
hacker@data~deleting-newlines:~$ /challenge/run | tr -d '\n'
Your line-split flag: pwn.college{MwLiuRkIiyyD8kSsfGfRfgYAITM.0VNxEzNxwSN0AzNzEzW}
```
    
### New Learnings
1. Deleting with tr -d: The main lesson is using the tr command with the -d flag to delete a specific set of characters from a stream of data.

2. Escaping Characters: The challenge shows that a backslash (\) is used to specify characters that are hard to input normally, like a newline (\n).

### References 
None