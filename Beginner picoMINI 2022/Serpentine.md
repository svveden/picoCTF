## Description

>Find the flag in the Python script!

Opening up the given `serpentine.py` file gives us the source code. I found that the `print_flag()` function is never actually called.

So, I changed the line where it was supposed to be called to:

```
elif choice == 'b':
      print_flag()
```

After rerunning the script with the function being called I got the key:

>picoCTF{7h3_r04d_l355_7r4v3l3d_ae743140}
