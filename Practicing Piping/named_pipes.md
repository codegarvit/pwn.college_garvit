# pwn.college_garvit
# Praciting Piping

# Named Pipes
This challenge introduces named pipes, also known as FIFOs (First In, First Out), which are created with the mkfifo command. These are special files that allow processes to communicate. The task is to create a FIFO, redirect the /challenge/run program's output into it, and read that output to get the flag. The challenge's key difficulty is managing the "blocking" behavior of FIFOs, which requires coordinating a reader and a writer process, typically in two separate terminals.

### Solve
**Flag:** `pwn.college{4uo3UdRLbxf4Sv0ruEtMVQLS6yz.01MzMDOxwSN0AzNzEzW}`
The solution requires using two terminals to manage the synchronized, blocking nature of the named pipe. One terminal acts as the "reader," and the other acts as the "writer."

1. Create the FIFO: The first step, performed in first terminal, is to create the named pipe file at the specified location.
mkfifo /tmp/flag_fifo

2. Start the Reader: In the first terminal, a command is run to read from the FIFO. The cat command is a simple and effective choice. After this command is executed, the terminal will block (hang), waiting for a writer to send data to the pipe.
cat /tmp/flag_fifo

3. Start the Writer: In a second, separate terminal, the /challenge/run program is executed with its standard output redirected to the same FIFO.
/challenge/run > /tmp/flag_fifo

4. Get the Flag: As soon as the command in Terminal 2 is executed, the connection is complete and the pipe unblocks. The /challenge/run program writes the flag into the pipe, and the waiting cat command in Terminal 1 reads the flag and prints it to the screen.

# Terminal 1:
```bash
hacker@piping~named-pipes:~$ mkfifo /tmp/flag_fifo
hacker@piping~named-pipes:~$ cat /tmp/flag_fifo
You've correctly redirected /challenge/run's stdout to a FIFO at
/tmp/flag_fifo! Here is your flag:
pwn.college{4uo3UdRLbxf4Sv0ruEtMVQLS6yz.01MzMDOxwSN0AzNzEzW}
```

# Terminal 1:
```bash
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo!
Bash will now try to open the FIFO for writing, to pass it as the stdout of
/challenge/run. Recall that operations on FIFOs will *block* until both the
read side and the write side is open, so /challenge/run will not actually be
launched until you start reading from the FIFO!
```
    
### New Learnings
1. Creating Named Pipes (mkfifo): The primary lesson is the use of the mkfifo command to create a persistent named pipe, a special file that can be used for inter-process communication.

2. FIFO Blocking Behavior: This challenge provides a hands-on demonstration of a key feature of FIFOs: they block write operations until a read operation opens the other end, and vice-versa. This is a form of automatic process synchronization.

### References 
None