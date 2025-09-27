# pwn.college_garvit
# Comprehending Commands

# Finding Files
This challenge introduces the powerful find command. The goal is to locate a file named flag that has been hidden in a random directory somewhere on the entire filesystem. The challenge notes that there may be decoy files or directories with the same name, and the search will generate many "Permission denied" errors that should be ignored.

### Solve
**Flag:** `pwn.college{QI_Z5_RVAAlWZNEjh5q-DLHeeA0.QXyMDO0wSN0AzNzEzW}`

1. Search the Filesystem: The find command is used to search the entire filesystem (starting from the root directory /) for any file with the exact name flag.

2. Filter the Results: This command produces a long list of "Permission denied" errors, which are ignored. It also provides a list of paths for every file or directory matching the name "flag".

3. Check Each Candidate: A process of trial and error is used with the cat command on each path found.
The first result (/usr/local/lib/python3.8/dist-packages/pwnlib/flag) turned out to be a directory.
The second result contained the correct flag.

```bash
hacker@commands~finding-files:~$ find / -name flag
find: ‘/root’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/tmp/tmp.4mK6TfTSUV’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/opt/busybox/busybox-1.33.2/include/config/feature/xargs/support/repl/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag
cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /opt/busybox/busybox-1.33.2/include/config/feature/xargs/support/repl/flag
pwn.college{QI_Z5_RVAAlWZNEjh5q-DLHeeA0.QXyMDO0wSN0AzNzEzW}hacker@commands~finding-files:~$
```
    
### New Learnings
1. find Command: The main takeaway is the syntax and usage of the find command: find <location> -name <filename> is a fundamental pattern for locating files.

2. Searching the Root Directory: Using / as the search location tells find to recursively search the entire filesystem.

3. Handling Errors: Real-world command-line usage often involves verbose output and errors. This challenge teaches you to parse through irrelevant information (like "Permission denied") to find the useful results.

4. Systematic Verification: It demonstrates that the first result isn't always the correct one, requiring a methodical process of checking each possibility.

### References 
None