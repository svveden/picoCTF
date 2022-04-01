## Description

>Can you crack the password to get the flag? Download the password checker here and you'll need the encrypted flag and the hash in the same directory too. Here's a dictionary with all possible passwords based on the password conventions we've seen so far.

For this one we have A LOT more passwords to go through and brute forcing like my previous method would take way too long.

So instead I just went through each line of the dictionary.txt file, hashed it using the given MD5 hasher and then compared.

```

def level_5_pw_check():
    f = open("dictionary.txt", "r")
    for i in f:
        user_pw = i.strip("\n")
        user_pw_hash = hash_pw(user_pw)
        if( user_pw_hash == correct_pw_hash ):
            print("Welcome back... your flag, user:")
            decryption = str_xor(flag_enc.decode(), user_pw)
            print(decryption)
            return
    print("That password is incorrect")

```

I then got the key: 
>Welcome back... your flag, user:
>
>picoCTF{h45h_sl1ng1ng_36e992a6}
