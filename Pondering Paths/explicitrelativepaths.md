# pwn.college_garvit
# Hello Hackers

# Implicit Relative Paths, from/
This challenge builds upon implicit relative paths by introducing explicit relative references like . (current directory) and .. (parent directory). These can be used to construct paths that still resolve to the same target.

Absolute paths always start with / and resolve independently of the current working directory (cwd), while relative paths are interpreted from the cwd. Using . and .., we can make relative paths more “explicit” but still valid.

### Solve
**Flag:** `pwn.college{YQ4cK8UNxKKfoG8QZCm8htDsP4e.QXwUTN0wSN0AzNzEzW}`
The task: execute the challenge binary using a relative path that explicitly includes . in its path expression.

1. Ensure the current working directory is root (/).
```bash
hacker@paths~explicit-relative-paths-from-:~$ cd /
```
2. From /, invoke the program using a relative path with .
```bash
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{YQ4cK8UNxKKfoG8QZCm8htDsP4e.QXwUTN0wSN0AzNzEzW}
```
The ./challenge/./run path resolves identically to challenge/run, but it explicitly uses . to reference the current directory.
### New Learnings
The key learnings are:

1. . refers to the current directory, and .. refers to the parent directory.
2. Absolute paths always begin with / and resolve independently of cwd.
3. Relative paths can include . and .. without changing the target, but they make the path more explicit.

### References 
None