# CTF Writeups

Writeups of Capture The Flag challenges I solve while learning offensive and defensive security.
I am a Computer Engineering student at Sapienza University of Rome, and this repository documents
my path into cybersecurity: for every challenge I explain the problem, my reasoning (including dead ends),
the solution and what I learned.

- Challenges solved on CyLab Academy (picoCTF), username: IlescuDumitru
- Contact: dumitruilescu8@gmail.com

## Writeups

| # | Challenge | Platform | Category | Difficulty | Key concepts |
|---|-----------|----------|----------|------------|--------------|
| 1 | [Obedient Cat](general-skills/obedient-cat.md) | picoCTF (CyLab Academy) | General Skills | Easy | Linux basics, `cat` |
| 2 | [Python wrangling](general-skills/python-wrangling.md) | picoCTF (CyLab Academy) | General Skills | Medium | Python scripts |
| 3 | [Mod 26](cryptography/mod-26.md) | picoCTF (CyLab Academy) | Cryptography | Easy | Caesar cipher and ROT13 |
| 4 | [Insp3ct0r](web-exploitation/Insp3ct0r.md) | picoCTF (CyLab Academy) | Web Exploitation | Easy | Structure of a web page |
| 5 | [Information](forensics/information.md) | picoCTF (CyLab Academy) | Forensics | Easy | Metadata, exiftool and base64 |

## Repository structure

One folder per category (`web-exploitation/`, `cryptography/`, `reverse-engineering/`, `forensics/`,
`binary-exploitation/`, `general-skills/`). Each writeup follows the same structure: see [TEMPLATE.md](TEMPLATE.md).

## Tools I use

Ubuntu on WSL, Python 3, CyberChef, Wireshark, Ghidra, Burp Suite Community, GDB.

## Ethics

I only publish writeups of challenges whose platforms allow it: PicoCTF picoGym practice challenges and
retired HackTheBox machines. I never publish solutions to active challenges or live competitions.
All techniques shown here were used only on systems built for practice.