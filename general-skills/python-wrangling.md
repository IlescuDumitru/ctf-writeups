# Python wrangling

| Platform | Category | Difficulty | Date solved |
|----------|----------|---------------------|-------------|
| picoCTF (CyLab Academy) | General-skills | medium | 2026-11-25 |

## Challenge

The challenge provides a python script (`ende.py`), an encrypted file (`flag.txt.en`) and a password (`password.txt`) and asks to recover the flag

## TL;DR

Run `ende.py` in decryption mode (`-d`) on `flag.txt.en` and enter the password from `password.txt` when prompted.

## Reasoning

1. The `.en` extension suggested the flag file was encrypted, and `file` confirmed it was a single line of ASCII text, not readable as-is.
2. Running `python3 ende.py` without arguments printed its usage: `ende.py (-e/-d) [file]`.
3. My first attempt was `python3 ende.py -e flag.txt.en`, which encrypted the already encrypted file a second time and printed a long string starting with `gAAAAA`.
4. Reading the source with `cat ende.py`, I saw that the script uses Fernet from the `cryptography` library, reads the mode (`-e` or `-d`) from the command-line arguments and asks for the password to use as the key. So `-d` was the right option.
5. Running it with `-d` and the password from `password.txt` printed the flag.

## Solution

```bash
 wget https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/ende.py
 wget https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/flag.txt.en
 wget https://challenge-files.cylabacademy.net/library/9524fad56d411feaebef2bff00dedd811236de9859d90c446ac88ffac47e0192/password.txt
 cat password.txt
 #prints the password
 python3 ende.py
 #Usage: ende.py (-e/-d) [file]
 python3 ende.py -d flag.txt.en
 # Please enter the password: <content of password.txt>
```

Flag: `academy{...}` (redacted)

## What I learned

- Running a script without arguments often shows its usage, which explains how to call it.
- Command-line arguments (`-e`, `-d`, file name) are read by Python through `sys.argv`.
- Fernet is a symmetric encryption scheme: the same key encrypts and decrypts, and its tokens start with `gAAAAA`.

## References

- [Fernet documentation (cryptography library)](https://cryptography.io/en/latest/fernet/)
