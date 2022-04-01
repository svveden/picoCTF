## Description

>Can you crack the password to get the flag? 
>Download the password checker here and you'll need the encrypted flag and the hash in the same directory too. 
>There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

Like the other two PW Crack problems, I'll just analyze the level3.py first.

I found this:

```pos_pw_list = ["f7f3", "4aa2", "8e1d", "2266", "7243", "9f43", "f634"]```

I'll just try each one.

`f634` worked.

>Please enter correct password for flag: f634
>
>Welcome back... your flag, user:
>
>picoCTF{m45h_fl1ng1ng_64840799}
