# pwn.college_garvit
# Comprehending Commands

# An Epic FIlesystem Quest
This challenge is a multi-step digital scavenger hunt designed to test filesystem navigation skills. Using only ls, cat, and cd, you must follow a long trail of clues starting from the root directory (/). Each clue reveals the location of the next, sometimes with special rules, until you finally uncover the flag.

### Solve
**Flag:** `pwn.college{MzChCVmwdKesONAekudN_utWTFY.QX5IDO0wSN0AzNzEzW}`

The solution involves carefully following each clue, paying close attention to special instructions like "trapped," "delayed," or "hidden."

1. The First Clue: The quest begins by finding and reading the TEASER file in the root directory. This clue is trapped, meaning you cannot cd to the next location.

2. The "Trapped" Clue: You must ls the target directory from afar to find the real filename (DISPATCH-TRAPPED) and then cat it using its full path.

3. The "Delayed" Clue: After navigating to a new directory, the next clue in the TRACE file is delayed, meaning you must cd into the next location for the clue to be readable.

4. The Secret & The Second Quest: Following the "delayed" clue's instructions, you cd into the new directory and find a SECRET file, which starts a whole new quest.

5. The "Hidden" Clue: The second quest involves another "trapped" clue, which eventually leads to a hidden clue. You must use the -a flag with ls to find the hidden file, .DOSSIER.

6. The Final Chain: Following the clues from .DOSSIER leads through a final chain of directories, testing the same mechanics again.

7. The Final Flag: The last clue leads to the _pycache_ directory, where the INSIGHT file contains the flag.

```bash
hacker@commands~an-epic-filesystem-quest:~$ cat /TEASER
Tubular find!
The next clue is in: /opt/linux/linux-5.4/include/linux/netfilter_bridge

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:~$ ls /opt/linux/linux-5.4/include/linux/netfilter_bridge
DISPATCH-TRAPPED  ebtables.h
hacker@commands~an-epic-filesystem-quest:~$ cat /opt/linux/linux-5.4/include/linux/netfilter_bridge/DISPATCH-TRAPPED
Great sleuthing!
The next clue is in: /usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Asana-Math/Monospace
hacker@commands~an-epic-filesystem-quest:~$ cd /usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Asana-Math/Monospace
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Asana-Math/Monospace$ ls
Regular  TRACE
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Asana-Math/Monospace$ cat TRACE
Tubular find!
The next clue is in: /opt/linux/linux-5.4/drivers/net/ethernet/marvell/mvpp2

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/SVG/fonts/Asana-Math/Monospace$ cd /opt/linux/linux-5.4/drivers/net/ethernet/marvell/mvpp2
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/marvell/mvpp2$ ls
Makefile  SECRET  mvpp2.h  mvpp2_cls.c  mvpp2_cls.h  mvpp2_debugfs.c  mvpp2_main.c  mvpp2_prs.c  mvpp2_prs.h
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/marvell/mvpp2$ cat SECRET
Great sleuthing!
The next clue is in: /usr/share/icons/hicolor/16x16/emotes

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/marvell/mvpp2$ ls /usr/share/icons/hicolor/16x16/emotes
SNIPPET-TRAPPED
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/marvell/mvpp2$ cat /usr/share/icons/hicolor/16x16/emotes/SNIPPET-TRAPPED
Lucky listing!
The next clue is in: /opt/linux/linux-5.4/net/unix

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/marvell/mvpp2$ ls -a /opt/linux/linux-5.4/net/unix
.         .af_unix.o.cmd   .scm.o.cmd              Makefile   built-in.a  garbage.o  scm.o
..        .built-in.a.cmd  .sysctl_net_unix.o.cmd  af_unix.c  diag.c      scm.c      sysctl_net_unix.c
.DOSSIER  .garbage.o.cmd   Kconfig                 af_unix.o  garbage.c   scm.h      sysctl_net_unix.o
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/marvell/mvpp2$ cat /opt/linux/linux-5.4/net/unix/.DOSSIER
Tubular find!
The next clue is in: /opt/linux/linux-5.4/Documentation/features/core/eBPF-JIT

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/marvell/mvpp2$ ls /opt/linux/linux-5.4/Documentation/features/core/eBPF-JIT
HINT-TRAPPED  arch-support.txt
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/marvell/mvpp2$ cat /opt/linux/linux-5.4/Documentation/features/core/eBPF-JIT/HINT-TRAPPED
Congratulations, you found the clue!
The next clue is in: /usr/lib/x86_64-linux-gnu/libgtk2.0-0
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/net/ethernet/marvell/mvpp2$ cd /usr/lib/x86_64-linux-gnu/libgtk2.0-0
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/libgtk2.0-0$ ls
CUE  gtk-query-immodules-2.0
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/libgtk2.0-0$ cat CUE
Tubular find!
The next clue is in: /usr/local/lib/python3.8/dist-packages/pyvex/lifting/gym/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/libgtk2.0-0$ cd /usr/local/lib/python3.8/dist-packages/pyvex/lifting/gym/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pyvex/lifting/gym/__pycache__$ ls
INSIGHT                  aarch64_spotter.cpython-38.pyc  x86_spotter.cpython-38.pyc
__init__.cpython-38.pyc  arm_spotter.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/pyvex/lifting/gym/__pycache__$ cat INSIGHT
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{MzChCVmwdKesONAekudN_utWTFY.QX5IDO0wSN0AzNzEzW}
```
### New Learnings
1. Systematic Navigation: This challenge reinforces the core Linux skill of navigating complex directory structures using ls, cat, and cd.

2. Reading Instructions Carefully: Success depends on paying close attention to keywords like "trapped," "delayed," and "hidden," which completely change the required command.

3. Using ls -a: The "hidden" clue specifically teaches the importance of the ls -a flag for finding files (like configuration files) that are normally not visible.

4. Absolute vs. Relative Paths: The "trapped" clues force the use of absolute paths (e.g., cat /path/to/file), while normal steps allow for the convenience of relative paths after using cd.

### References 
None