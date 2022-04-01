## Description

> Files can always be changed in a secret way. Can you find the flag? cat.jpg

I downloaded cat.jpg and guessed that the flag was going to be hidden as a string or something inside the photo itself. So, I opened up the photo as a text file and got the following output:

``` <rdf:Description rdf:about=''
  xmlns:cc='http://creativecommons.org/ns#'>
  <cc:license rdf:resource='cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9'/>
 </rdf:Description>
 ```
 I guessed the ```cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9``` was probably base64 and sure enough: picoCTF{the_m3tadata_1s_modified}
