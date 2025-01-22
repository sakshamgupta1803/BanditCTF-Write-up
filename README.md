# OverTheWire Bandit CTF Level 0-12 Writeup

![Screenshot from 2024-12-26 14-11-36](https://github.com/user-attachments/assets/b02b51d0-c8f9-4897-92ac-451b3448832d)

## :clipboard: Table of Contents

- [:open_book: Introduction](#open_book-introduction)
- [:triangular_flag_on_post: Bandit Level 0](#triangular_flag_on_post-bandit-level-0)
- [:triangular_flag_on_post: Bandit Level 0 - 1](#triangular_flag_on_post-bandit-level-00---01)
- [:triangular_flag_on_post: Bandit Level 1 - 2](#triangular_flag_on_post-bandit-level-01---02)
- [:triangular_flag_on_post: Bandit Level 2 - 3](#triangular_flag_on_post-bandit-level-02---03)
- [:triangular_flag_on_post: Bandit Level 3 - 4](#triangular_flag_on_post-bandit-level-03---04)
- [:triangular_flag_on_post: Bandit Level 4 - 5](#triangular_flag_on_post-bandit-level-04---05)
- [:triangular_flag_on_post: Bandit Level 5 - 6](#triangular_flag_on_post-bandit-level-05---06)
- [:triangular_flag_on_post: Bandit Level 6 - 7](#triangular_flag_on_post-bandit-level-06---07)
- [:triangular_flag_on_post: Bandit Level 7 - 8](#triangular_flag_on_post-bandit-level-07---08)
- [:triangular_flag_on_post: Bandit Level 8 - 9](#triangular_flag_on_post-bandit-level-08---09)
- [:triangular_flag_on_post: Bandit Level 9 - 10](#triangular_flag_on_post-bandit-level-09---10)
- [:triangular_flag_on_post: Bandit Level 10 - 11](#triangular_flag_on_post-bandit-level-10---11)
- [:triangular_flag_on_post: Bandit Level 11 - 12](#triangular_flag_on_post-bandit-level-11---12)

## :open_book: Introduction
Over The Wire is a Warfare based game which is generally used by people who have started their CTF journey.

![Screenshot from 2024-12-26 22-20-48](https://github.com/user-attachments/assets/b613193c-de04-40e1-9b82-4052145a766a)

One of their challenges is Bandit CTF which is composed of different levels, each level being more tricky than the previous one.

![Screenshot from 2024-12-26 22-22-19](https://github.com/user-attachments/assets/e4817015-1f00-4a5d-8062-ea25ba621ec6)

Here is my solution to the 12 levels in Bandit CTF.. Here We Go!!!

## :triangular_flag_on_post: Bandit Level 0
### Description:

Level 0 is the beginning to your Bandit CTF journey..

![Screenshot from 2024-12-26 22-29-17](https://github.com/user-attachments/assets/1de5f2f3-dfdd-4f07-8898-dcee0fc21ea6)
### Problem Statement:

We need to find how to connect the bandit.labs.overthewire.org on the port 2220 using ssh.

### Solution:
```
ssh -p 2220 bandit0@bandit.labs.overthewire.org
```
Password : bandit0

After entering the password , we would be able to access the bandit0 shell.

## :triangular_flag_on_post: Bandit Level 0 - 1
### Problem Statement:

This level asks you to access the readme file present in the bandit0 shell which would contain the password to Level 1

### Solution: 
```
bandit0@bandit:~$ cat readme
```
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walkthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!

The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

After getting the password, we will exit from the bandit0 shell to enter the next level.

## :triangular_flag_on_post: Bandit Level 1-2 
### Problem Statement:

This level asks you to dashed file present in the home directory of bandit1

### Solution:

Dashed filename is difficult to access using cat command i.e it needs a special command to access the contents of that file..

```
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat <-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
bandit1@bandit:~$ exit
logout
```
After getting the password, we will exit from the bandit1 shell to enter the next level.
```
Password : 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

## :triangular_flag_on_post: Bandit Level 2-3 
### Problem Statement:

This level asks you to access the file which has spaces in it.

### Solution:

Here in this case also there is a special command of cat to access spaces in the filename.

```
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat 'spaces in this filename'
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
bandit2@bandit:~$ exit
logout
```
After getting the password, we will exit from the bandit2 shell to enter the next level.
```
Password : MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```
## :triangular_flag_on_post: Bandit Level 3-4
### Problem Statement:

It asks you to find the password present in the hidden file in inhere directory..

### Solution:

```
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ find
.
./...Hiding-From-You
bandit3@bandit:~/inhere$ cat ./...Hiding-From-You
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
bandit3@bandit:~/inhere$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```

After getting the password, we will exit from the bandit3 shell to enter the next level.
```
Password : 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```
## :triangular_flag_on_post: Bandit Level 4-5
### Problem Statement:

The password of this level is the only human readable file in the inhere directory

### Solution:

```
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ file ./-file0*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: data
bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
bandit4@bandit:~/inhere$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
After getting the password, we will exit from the bandit4 shell to enter the next level.
```
Password : 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```
## :triangular_flag_on_post: Bandit Level 5-6
### Problem Statement:

We have to find the password which is stored in the file which is human readable,1033 in size and not executable.

### Solution : 
```
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ find -type f -readable -size 1033c ! -executable
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
bandit5@bandit:~/inhere$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
After getting the password, we will exit from the bandit5 shell to enter the next level.
```
Password : HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```
## :triangular_flag_on_post: Bandit Level 6-7
### Problem Statement:

We have to find the password which is stored in the file which is in the group bandit6 , user bandit7 and size 33 bytes.

### Solution:

```
bandit6@bandit:~$ find -type f -group bandit6 -user bandit7 -size 33c 2>/dev/null
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
bandit6@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
After getting the password, we will exit from the bandit6 shell to enter the next level.
```
Password : morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
```
## :triangular_flag_on_post: Bandit Level 7-8
### Problem Statement:

The password for this level is next to the word millionth.

### Solution:

```
bandit7@bandit:~$ grep -w "millionth" data.txt
millionth	dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
bandit7@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
After getting the password, we will exit from the bandit7 shell to enter the next level.
```
Password : dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
## :triangular_flag_on_post: Bandit Level 8-9
### Problem Statement:

The password for this level is stored in the file data.txt and the password is the only unique line in the file.

### Solution:

```
bandit8@bandit:~$ sort data.txt | uniq -u
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
bandit8@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
After getting the password, we will exit from the bandit8 shell to enter the next level.
```
Password : dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
## :triangular_flag_on_post: Bandit Level 9-10
### Problem Statement:

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

### Solution:

```
bandit9@bandit:~$ strings data.txt
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```
After getting the password, we will exit from the bandit9 shell to enter the next level.
```
Password : FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
```
## :triangular_flag_on_post: Bandit Level 10-11
### Problem Statement:

The password is stored in data.txt which is base64 encoded.

### Solution:
```
bandit10@bandit:~$ base64 --decode data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
bandit10@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
After getting the password, we will exit from the bandit10 shell to enter the next level.
```
Password : dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
## :triangular_flag_on_post: Bandit Level 11-12
### Problem Statement:

The password is stored in data.txt which is encoded using ROT13 cipher.

### Solution:
```
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
bandit11@bandit:~$ echo "7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
bandit11@bandit:~$ exit
logout
Connection to bandit.labs.overthewire.org closed.
```
After getting the password, we will exit from the bandit11 shell to enter the next level.
```
Password : 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```
