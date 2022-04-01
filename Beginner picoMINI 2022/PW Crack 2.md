## Description

>Can you crack the password to get the flag? 
>Download the password checker here and you'll need the encrypted flag in the same directory too.

After opening the given python script level2.py, I find that it's pretty much the same as PW Crack 1, except this time, the password is "hidden" as hex values instead of ascii.

```
user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x35) + chr(0x39) + chr(0x30) + chr(0x39) ):
        print("Welcome back... your flag, user:")
```
I wrote a python scrip that just prints those characters

`print(chr(0x35) + chr(0x39) + chr(0x30) + chr(0x39))`

This is what I got: 
```
$ python print.py 
5909
```
After rerunning the level2.py script and putting `5909` as the password I got the key:

>Please enter correct password for flag: 5909

>Welcome back... your flag, user:

>picoCTF{tr45h_51ng1ng_b0539d96}
