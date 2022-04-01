## Description

>Fix the syntax error in the Python script to print the flag.

After downloading the given python script and running it, I got this syntax error: 

```
$ python fixme2.py 
  File "/home/kali/Desktop/picoCTF/fixme2.py", line 22
    if flag = "":
            ^
SyntaxError: invalid syntax
```
So the problem here is the use of `=` instead of `==` for a comparison.

After opening the file and finding the problematic line:

```
# Check that flag is not empty
if flag = "":
  print('String XOR encountered a problem, quitting.')
else:
  print('That is correct! Here\'s your flag: ' + flag)
  ```
  
and changing it to the correct `==`

```
# Check that flag is not empty
if flag == "":
  print('String XOR encountered a problem, quitting.')
else:
  print('That is correct! Here\'s your flag: ' + flag)
  ```
then rerunning the script, I got the key: 
  
>That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_b4d595d9}
