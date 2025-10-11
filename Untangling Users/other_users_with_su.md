# pwn.college_garvit
# Untangling Users

# Other Users With su
This challenge shows how to give a username as an argument to switch users with the su command, instead of just switching to root. The task is to switch to the zardus user using a given password to get the flag. 


### Solve
**Flag:** `pwn.college{8nSR_XSv-N5fA8SH0EtZng5_qwF.QX2UDN1wSN0AzNzEzW}`
The solution is an interactive process where you run the su command with the target username and then enter the password provided in the challenge.

1. The Goal: The challenge requires you to "switch to the zardus user" before you "run /challenge/run".
2. The Process:
 - First, the su command is run with zardus as an argument.
 - The command will then ask for a Password:. The password given in the challenge, dont-hack-me, is typed, and Enter is pressed.
 - 0After this, the command line shows that you have "become Zardus" by changing the username in the prompt to zardus@....
 
3. Getting the Flag: Now running as the zardus user, the challenge program is executed, leading to the flag.

```bash
hacker@users~other-users-with-su:~$ su zardus
Password:
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{8nSR_XSv-N5fA8SH0EtZng5_qwF.QX2UDN1wSN0AzNzEzW}
```
    
### New Learnings
1. su <username>: The main lesson is that we can give a username as an argument to switch users. This allows us to take on the identity of another user, provided we know their password.
2. Changing User Context: This challenge shows how to change your user identity in the shell. When we switch to another user, we run commands with that user's permissions.

### References 
None