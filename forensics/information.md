# Information

| Platform | Category | Difficulty | Date solved |
|----------|----------|---------------------|-------------|
| picoCTF (CyLab Academy) | Forensics | Easy | 2026-11-27 |

## Challenge

The challenge provides the file `cat.jpg` and asks to search the flag in its metadata.

## TL;DR

The flag is hidden in the file's metadata, in the license field, encoded in base64. Read the metadata with `exiftool` and decode the string. 

## Reasoning

1. Metadata is extra information stored inside a file. The tool `exiftool` reads it. 
2. After checking the metadata of `cat.jpg` i saw that the license looked like a random string.
3. Base64 is an encoding that turns data into letters, numbers, `+`, `/` and often ends with `=`. The string looked similar so i tried decoding it with `base64 -d` and got the flag. 

## Solution

```bash
wget https://challenge-files.cylabacademy.net/library/c585b4adbdaa06f409db7bf5012c2e58e9aab24669764a5f1cf0f9ce0d60dcfd/cat.jpg
exiftool cat.jpg
echo '<YWNhZGVteXt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9>' | base64 -d
```

Flag: `academy{...}` (redacted)

## What I learned

- How to check the metadata of a file with `exiftool`.
- The metadata can be changed, so it can hide informations.
- how base64 works and how a base64 string looks.

## References

- [exiftool manual page](https://exiftool.org/exiftool_pod.html)
- [base64(1) manual page](https://man7.org/linux/man-pages/man1/base64.1.html)