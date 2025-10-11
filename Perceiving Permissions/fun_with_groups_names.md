# pwn.college_garvit
# Perceiving Permissions

# Changing File Ownership
In this challenge, we learn that a user does not always belong to a group with the same name. The challenge has "randomized the name of the group that your user is in". We will need to use the id command to figure that name out, then chgrp to victory.

### Solve
**Flag:** `pwn.college{QLbSTX2Z_0M58zUdwG0dUf-Krn4.QXycjM1wSN0AzNzEzW}`
The solution is a three-step process where we first discover our randomized group name, change the ownership of the /flag file, and then read it.

1. The Goal: The challenge tells us that using hacker as the group name "is not going to work". We must first find the correct group name for our user.

2. Finding the Group Name: We use the id command as instructed by the challenge.
The output, uid=1000(hacker) gid=1000(grp1275) groups=1000(grp1275), shows that the group name is grp1275 and its ID number is 1000.

3. Changing Group Ownership: We use chgrp to change the group of the /flag file. We can use either the group name or the group ID.

4. Reading the Flag: With the group of the /flag file changed to a group we are a member of, we can now read the file with cat. This prints the flag.

```bash
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp1275) groups=1000(grp1275)
hacker@permissions~fun-with-groups-names:~$ chgrp 1000 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
pwn.college{QLbSTX2Z_0M58zUdwG0dUf-Krn4.QXycjM1wSN0AzNzEzW}
```
    
### New Learnings
1. Using the id command: The main lesson is that we need to use the id command to figure thae name out when we are unsure of the group that user is in.

2. Group Names and IDs: We learned that groups have both a name (like grp1275) and a number (gid=1000). Commands like chgrp can often use either one.

### References 
None