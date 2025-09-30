# pwn.college_garvit
# Digesting Documentation

# Searching For Manuals
This challenge teaches how to find a manual page when its exact name is unknown. The man page for this level's challenge is hidden with a randomized name. The task is to first learn how to search the manual page database by reading the manual for man itself, use that skill to find the hidden manual, and finally extract the secret option needed to get the flag from the /challenge/challenge program.

### Solve
**Flag:** `pwn.college{4BDRWBpyp8kqW5PTa3SkfOKGSzY.QX0ITO0wSN0AzNzEzW}`

The solution requires a multi-step process of learning, searching, and executing, as guided by the challenge prompts.

1. Learning How to Search: The first step is to learn about man's advanced features by running man man. This reveals the -k option, which allows searching for manual pages by keyword.

2. Finding the Hidden Manual: The -k option is then used with the keyword "challenge" to search the database.
man -k challenge
This command reveals the hidden manual's name is lgafnadaet.

3. Discovering the Secret Option: With the correct name found, the hidden manual is read to find the arguments for the program.
man lgafnadaet
This manual's DESCRIPTION section specifies that the option --lgafrna with the value 889 will print the flag.

4. Executing the Final Command: HINT 2 of the challenge specifies that the program to run is still /challenge/challenge. The secret option and value are passed to this program to get the flag.
/challenge/challenge --lgafrna 889
This command successfully prints the flag: pwn.college{8898lLLg12mAMk2fEnad9ABaWety.QX2EDO0wSN0AzNzEzW}.

```bash
codegarvit@LAPTOP-ECLRKBA4:~$ ssh -i ~/.ssh/pwn_key hacker@dojo.pwn.college
Connected!
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
lgafnadaet (1)       - print the flag!
hacker@man~searching-for-manuals:~$ man lgafnadaet
hacker@man~searching-for-manuals:~$ /challenge/challenge --lgafna 889
Correct usage! Your flag: pwn.college{8898lLg12MaMK2fEnad9ABaWety.QX2EDO0wSN0AzNzEzW}
```
    
### New Learnings
1. man -k (Keyword Search): The main lesson is the use of the man -k command (also known as apropos) to search the short descriptions of all manual pages. This is extremely useful when you know what a command does but can't remember its name.

2. Multi-Stage Problem Solving: This challenge demonstrates a common workflow in technical fields: first learn how to use a tool, then use that tool to find necessary information, and finally use that information to solve the actual problem.

### References 
None