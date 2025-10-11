# pwn.college_garvit
# Untangling Users

# Cracking Passwords
This challenge explains that Linux passwords are not stored directly, but as one-way hashes in the /etc/shadow file. It introduces the famous John the Ripper (john) tool, which can crack these hashes if the file is leaked. The task is to crack the password for the zardus user from a leaked file, then su to zardus, and run /challenge/run to get the flag.

### Solve
**Flag:** `pwn.college{M_BmPORYDbTogg4VF8-lsgt9N9j.QX3UDN1wSN0AzNzEzW}`
The solution requires us to first use john to find the password, then use that password with su to become the zardus user.

1. The Goal: The /challenge/run command states, "You MUST become the zardus user before executing this command". To do this, we need to find Zardus' password.

2. Cracking the Password: We use the john command on the leaked file provided by the challenge.
After the "Session completed", the output shows the cracked password is aardvark for the user (zardus).

3. Becoming Zardus: Now that we have the password, we use su to switch to the zardus user.
When asked for the Password, we enter the password we just cracked: aardvark.

4. Getting the Flag: After we have become Zardus, we can run the final command to print the flag.

```bash
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:18 100% 2/3 0.05356g/s 311.8p/s 311.8c/s 311.8C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{M_BmPORYDbTogg4VF8-lsgt9N9j.QX3UDN1wSN0AzNzEzW}
```
    
### New Learnings
1. Password Hashes: We learned that passwords are not stored as plain text but are "one-way-encrypting (hashing)" into a stored hash that su compares against.

2. John the Ripper (john): We learned how to use the john tool to crack password hashes from a leaked password shadow-file.

3. Shadow File Security: This challenge shows why the /etc/shadow file's security is so important. Unlike /etc/passwd, it is not a globally-readable file because if a "hacker gets their hands on a leaked /etc/shadow, they can start cracking passwords.
### References 
None