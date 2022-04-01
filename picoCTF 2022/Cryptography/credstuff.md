## Description

>We found a leak of a blackmarket website's login credentials. Can you find the password of the user cultiris and successfully decrypt it? Download the leak here. The first user in usernames.txt corresponds to the first password in passwords.txt. The second user corresponds to the second password, and so on.

After opening the usernames.txt file and ctrl+f the name 'cultiris', I found it on line 378.

Line 378 in the passwords.txt sections gives us `cvpbPGS{P7e1S_54I35_71Z3}` which looks an awful lot like a picoCTF flag.

This isn't encrpyted with anything serious, probably just ceaser cipher shifting.

After shifting it by 13 spaces and modulo 26, I got the key: 

>picoCTF{C7r1F_54V35_71M3}
