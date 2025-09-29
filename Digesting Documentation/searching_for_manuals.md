# pwn.college_garvit
# Digesting Documentation

# Searching Manuals
This challenge builds on the previous level by introducing the search functionality within man pages. The manual for the challenge program is intentionally populated with numerous decoy options to make manual reading inefficient. The task is to use the search feature (the / key) to quickly locate the specific option that will cause the program to print the flag.

### Solve
**Flag:** `pwn.college{4BDRWBpyp8kqW5PTa3SkfOKGSzY.QX0ITO0wSN0AzNzEzW}`

The solution involves systematically using the man page's built-in search function to find the needle in the haystack.
1. Open the Manual: First, the manual for the challenge program is opened.

2. Initiate a Search: Once inside the manual, pressing the / key initiates a forward search. Since the goal is to find the flag, the most logical search term is "flag".

3. Navigate Results: The initial search results land on general descriptions. Pressing the n key navigates to the next match. After pressing n a few times, the search highlights the following line:
--zzt This argument will give you the Flag!

4. Execute the Command: After discovering the secret option is --zzt, you quit the manual by pressing q and then run the challenge program with the correct argument.

```bash
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --zzt
Initializing...
Correct usage! Your flag: pwn.college{Ez8Wo2X7ddAvyV103FtNKh5plb5.QX1EDO0wSN0AzNzEzW}
```
    
### New Learnings

1. Searching in Manuals: The core lesson is how to use the search feature in man pages. Pressing / searches forward, ? searches backward, and n / N navigate to the next/previous match. 

2. Efficient Information Filtering: This challenge demonstrates a practical method for dealing with information overload. Instead of reading every line, you can identify keywords related to your goal and search for them directly.

3. Critical Reading: The exercise reinforces that you must actively look for clues within documentation, as the correct answer is often hidden among irrelevant or misleading information.

### References 
None