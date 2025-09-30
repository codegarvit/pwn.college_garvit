# pwn.college_garvit
# Shell Variables

# Printing Variables
This challenge introduces shell variables as a way to store data within a terminal session. It explains that to access the value of a variable, its name must be prefixed with a dollar sign ($). The task is to use the echo command to print the value of a pre-defined variable named FLAG.  

### Solve
**Flag:** `pwn.college{Y0Rg9qvc8bK5rOqILoAASM63xwp.QXwgDN1wSN0AzNzEzW}`
1. The Goal: The challenge explicitly states that the flag has been put into a variable called "FLAG" and that the shell must be used to print it out.

2. The Technique: The prompt shows that variables are printed with the echo command and that the variable name must be prepended with a $ to access its value. Forgetting the $ would cause the command echo FLAG to print the literal word "FLAG", not its contents.

3. The Final Command: The correct command combines echo with the variable $FLAG.
When this is run, the shell first sees $FLAG and replaces it with the secret value (the flag) that is stored inside it. Then, the echo command runs and prints that value to the screen.
The complete command is:
```bash
codegarvit@LAPTOP-ECLRKBA4:~$ ssh -i ~/.ssh/pwn_key hacker@dojo.pwn.college
Connected!
hacker@variables~printing-variables:~$ echo $FLAG
pwn.college{QSFf7jq86JLmVnE0rVosL9eT-ju.QX3UTN0wSN0AzNzEzW}
```
    
### New Learnings
1. Shell Variables: The primary lesson is the concept of shell variables, which are used to store data like text strings or numbers within a shell session.

2. Accessing Variable Values ($): The fundamental syntax for retrieving the contents of a variable is to prefix its name with a dollar sign ($). This is known as variable expansion.

3. echo Command: This challenge provides further practice with the echo command, a basic shell builtin used for displaying text and the contents of variables.

### References 
None