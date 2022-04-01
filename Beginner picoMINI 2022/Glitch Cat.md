## Description

>Our flag printing service has started glitching! 
>$ nc saturn.picoctf.net 55984

I talked to the server with the given command, and look at what I got:

>'picoCTF{gl17ch_m3_n07_' + chr(0x38) + chr(0x39) + chr(0x38) + chr(0x61) + chr(0x33) + chr(0x66) + chr(0x61) + chr(0x36) + '}'

Well, the keys definitely there, but obviously the 'glitch' is it's printing out the hex conversions of the ascii characters without converting them, maybe someone added an extra `"`?

Lets drop the output into a python script that just does one thing: print.

```
print('picoCTF{gl17ch_m3_n07_' + chr(0x38) + chr(0x39) + chr(0x38) + chr(0x61) + chr(0x33) + chr(0x66) + chr(0x61) + chr(0x36) + '}')
```
After running my script, I got the key: 

>picoCTF{gl17ch_m3_n07_898a3fa6}
