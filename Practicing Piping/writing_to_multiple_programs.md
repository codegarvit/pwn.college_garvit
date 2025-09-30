# pwn.college_garvit
# Praciting Piping

# Writing To Multiple Programs
This challenge introduces process substitution for output using the >(command) syntax. This shell feature allows a program's standard input to be treated as a writable file. The task is to use this feature, in combination with the tee command and standard pipes, to duplicate the output of one program (/challenge/hack) and send it simultaneously to the standard input of two other programs (/challenge/the and /challenge/planet).

### Solve
**Flag:** `pwn.college{Y0Rg9qvc8bK5rOqILoAASM63xwp.QXwgDN1wSN0AzNzEzW}`
The goal is to split the data stream from /challenge/hack and direct it to two separate programs. This is accomplished by building a sophisticated pipeline that uses tee to do the splitting.

1. The Tools: The solution relies on three shell features working together:
 - The tee command, which reads from standard input and writes to both standard output and any files given as arguments.
 - A standard pipe (|), which connects the standard output of one command to the standard input of another.
 - Process substitution (>(command)), which makes the standard input of a command look like a file that tee can write to.

2. Command Construction: The pipeline is constructed to manage the flow of data:
 - The process starts with the source program, /challenge/hack, whose output is piped to tee.
 - One destination program, /challenge/the, receives its input from tee's standard output via a standard pipe (|).
 - The second destination program, /challenge/planet, is made to look like a "file" by using process substitution. The expression >(/challenge/planet) becomes a file argument for tee.

The complete command is:
```bash
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >(/challenge/planet) | /challenge/the
Congratulations, you have duplicated data into the input of two programs! Here
is your flag:
pwn.college{Y0Rg9qvc8bK5rOqILoAASM63xwp.QXwgDN1wSN0AzNzEzW}
```
    
### New Learnings
1. Output Process Substitution >(command): The main lesson is the use of this syntax to allow a program that normally writes to a file (like tee) to instead send its data to the standard input of another command.

2. tee with Processes: This challenge demonstrates how to extend tee's functionality. By combining it with process substitution, tee can be used to split a data stream and send it to multiple other running programs, not just static files.

### References 
None