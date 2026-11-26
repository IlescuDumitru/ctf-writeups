# Obedient Cat

| Platform | Category | Difficulty | Date solved |
|----------|----------|---------------------|-------------|
| picoCTF (CyLab Academy) | general-skills | Easy | 2026-11-24 |

## Challenge

The challenge provides a file called `flag` and asks to find the flag inside of it.

## TL;DR

The flag is stored inside the file as a plain text so printing the file with `cat` reveals it.

## Reasoning

1. The name obedient cat reminded me of the `cat` command and the challenge stated that the answer was "in plain sight".
2. I downloaded the file  using `wget`.
3. Using `file flag` i saw that the file was an ASCII text.
4. I tried using `cat flag` and it read the flag on the terminal.

## Solution

```bash
wget https://challenge-files.cylabacademy.net/library/11b9e730524b026e2bce9e561dad9e8f1905b575e3fc6a1477eb1698b59e6585/flag
file flag
#output: flag: ASCII text
cat flag
```

Flag: `academy{...}` (redacted)

## What I learned

- `man <command>` opens the manual of the command as i did with `man cat`
- `cat` prints the content of a file; `wget` downloads a file from a URL and `file` identifies a file's type


## References


- [cat manual page](https://man7.org/linux/man-pages/man1/cat.1.html)
