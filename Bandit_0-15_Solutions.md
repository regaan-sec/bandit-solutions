
# OverTheWire Bandit Solutions (Levels 0–15)

This repository contains my notes and solutions for the [OverTheWire Bandit Wargame](https://overthewire.org/wargames/bandit/).  
I completed Levels 0 through 15 in **one day** as part of my cybersecurity journey.

---

## 📂 Level 0 → 1
**Task:** SSH into bandit0 and find the password for the next level.  
**Command:**
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
cat readme
```
**Password:** (hidden)

---

## 📂 Level 1 → 2
**Task:** The password is stored in a file called `-`.  
**Command:**
```bash
cat ./-
```
**Password:** (hidden)

---

## 📂 Level 2 → 3
**Task:** Password stored in a file with spaces in the name.  
**Command:**
```bash
cat "spaces in this filename"
```
**Password:** (hidden)

---

## 📂 Level 3 → 4
**Task:** Hidden file in the `inhere` directory.  
**Command:**
```bash
ls -a inhere
cat inhere/.hidden
```
**Password:** (hidden)

---

## 📂 Level 4 → 5
**Task:** Find human-readable file among many.  
**Command:**
```bash
file inhere/*
cat inhere/-file07
```
**Password:** (hidden)

---

## 📂 Level 5 → 6
**Task:** Find a file that is human-readable, 1033 bytes in size, not executable.  
**Command:**
```bash
find inhere/ -size 1033c ! -executable -type f
cat inhere/maybehere07/.file2
```
**Password:** (hidden)

---

## 📂 Level 6 → 7
**Task:** Find a file owned by user bandit7, group bandit6, size 33 bytes.  
**Command:**
```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```
**Password:** (hidden)

---

## 📂 Level 7 → 8
**Task:** Find the line with the word "millionth".  
**Command:**
```bash
grep millionth data.txt
```
**Password:** (hidden)

---

## 📂 Level 8 → 9
**Task:** Password stored in a file with repeated lines.  
**Command:**
```bash
sort data.txt | uniq -u
```
**Password:** (hidden)

---

## 📂 Level 9 → 10
**Task:** Find human-readable strings in a binary.  
**Command:**
```bash
strings data.txt | grep =
```
**Password:** (hidden)

---

## 📂 Level 10 → 11
**Task:** Decode Base64 encoded file.  
**Command:**
```bash
cat data.txt | base64 -d
```
**Password:** (hidden)

---

## 📂 Level 11 → 12
**Task:** File has been encoded multiple times with ROT13.  
**Command:**
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
**Password:** (hidden)

---

## 📂 Level 12 → 13
**Task:** File is a hexdump of a compressed file.  
**Commands:**
```bash
xxd -r data.txt > data
file data
mv data data.gz
gunzip data.gz
# repeat extracting until password file is revealed
```
**Password:** (hidden)

---

## 📂 Level 13 → 14
**Task:** Login using a private SSH key.  
**Command:**
```bash
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```
**Password:** (hidden)

---

## 📂 Level 14 → 15
**Task:** Submit password on localhost port 30000 using netcat.  
**Command:**
```bash
cat /etc/bandit_pass/bandit14 | nc localhost 30000
```
**Password:** (hidden)

---

# ✅ Reflection
In just one day, I learned and practiced:
- Linux navigation and hidden files
- File permissions and search with `find`
- Strings, sorting, uniqueness with `uniq`
- Encoding/decoding with `base64` and `ROT13`
- File compression and extraction (gzip, bzip2, tar)
- Networking basics with `nc`

This builds the foundation for real-world hacking, privilege escalation, and OSCP prep.

---

📂 GitHub Repo: [link here]  
📝 Blog: [Medium Link]  
🎥 YouTube: [Video Link]
