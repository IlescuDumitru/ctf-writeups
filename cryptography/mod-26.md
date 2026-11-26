# Mod 26

| Platform | Category | Difficulty | Date solved |
|----------|----------|---------------------|-------------|
| picoCTF (CyLab Academy) | Cryptography | Easy | 2026-11-26 |

## Challenge

The challenge asks to decode the flag encrypted in `values.txt` using ROT13.

## TL;DR

Print the content of `values.txt`, then replace every letter with the one 13 places after in the alphabet (ROT13).

## Reasoning

1. ROT13 is a Caesar cipher with a shift of 13.
2. Using `cat values.txt` I get a text that is clearly the flag after applying ROT13 :tn starts with `npnqrzl`, which is `academy` after ROT13.
3. I apply ROT13 again to recover the original flag.

## Solution


```bash
wget https://challenge-files.cylabacademy.net/library/4fcb791279e59f04dfab5d84570e0521973b63b01a5ba24cb69c7ea737cae863/values.txt
cat values.txt
#prints the flag after ROT13
cat values.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
# applies ROT13 and prints the flag
```

Flag: `academy{...}` (redacted)

## What I learned

- How ROT13 works, and that it is not a real encryption since there is no key.
- Applying ROT13 twice on a string gives back the original string: there are 26 letters in the alphabet and 2 x 13 = 26 ≡ 0 (mod 26) so shifting twice is the same as not shifting

## References

[ROT13 (wikipedia)](https://en.wikipedia.org/wiki/ROT13)
