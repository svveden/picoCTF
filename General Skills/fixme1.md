## Description

>Fix the syntax error in this Python script to print the flag.

After downloading the given python script and running it, I got the following syntax error:

`$ python fixme1.py   
  File "/home/kali/Desktop/picoCTF/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
`

After opening the given file, I found the issue here: 

`flag = str_xor(flag_enc, 'enkidu')
  print('That is correct! Here\'s your flag: ' + flag)`
  
 Unlike in the best language, C, python gets rather upset if you add unecessary spaces.
 
 After changing it to 
 `flag = str_xor(flag_enc, 'enkidu')
  print('That is correct! Here\'s your flag: ' + flag)`
  
 And rerunning the script, I got the flag: 
 
 > That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_05a3c38c}
