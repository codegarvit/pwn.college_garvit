# pwn.college_garvit
# Shell Variables

# Reading Input
This challenge introduces the env command as a method for viewing all exported variables, also known as environment variables. The task is to execute the env command and look through its output to find the value of the pre-set FLAG variable.

### Solve
**Flag:** `pwn.college{4EAC85o3PvOWKxGuVD7c7qv-jya.QX5UTN0wSN0AzNzEzW}`
The solution requires using the env command to inspect the shell's environment and locate the specific FLAG variable.

The Goal: The flag is stored in an exported variable named FLAG, which means it's part of the shell's environment and can be seen by other processes.

The Tool: The env command is the tool for this task. When run without arguments, it prints a list of all current environment variables and their values to standard output.

Execution: The simplest method is to run the env command and visually scan the output for the line starting with FLAG=.



```bash
hacker@variables~printing-exported-variables:~$ env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
PWD=/home/hacker
MANPATH=/run/dojo/share/man:
DOJO_AUTH_TOKEN=11530178f795ba4467995d51e2c3ca39ae8d0a5a9365a6c9dfc058941d14156d
HOME=/home/hacker
LANG=C.UTF-8
FLAG=pwn.college{cMMo8ory6_07VhG6iTqcZL3k_v0.QX4UTN0wSN0AzNzEzW}
TERMINFO=/run/dojo/share/terminfo
TERM=xterm-256color
SHLVL=2
LC_CTYPE=C.UTF-8
SSL_CERT_FILE=/run/dojo/etc/ssl/certs/ca-bundle.crt
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
```
    
### New Learnings
1. The env Command: The main lesson is the use of the env command to list all exported (environment) variables in the current shell session.

### References 
None