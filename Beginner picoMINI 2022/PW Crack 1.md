## Description

>Can you crack the password to get the flag? 
>Download the password checker here and you'll need the encrypted flag in the same directory too.

Let's open the level1.py file given for checking the inputted password.

```
def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "17ac"):
        print("Welcome back... your flag, user:")
```

Well that's an interesting if statement....

Running the script and putting `17ac` as the password gives us the key.

>picoCTF{545h_r1ng1ng_7719ae74}
