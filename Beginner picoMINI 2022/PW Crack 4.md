## Description

>Can you crack the password to get the flag? Download the password checker here and you'll need the encrypted flag and the hash in the same directory too. 
>There are 100 potential passwords with only 1 being correct. 
>You can find these by examining the password checker script.

Well this is a bit more time consuming since there are 100 possible passwords, so instead I'll write a short C script to go through each possible password for me:

```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>

int main(void){
	char *str = "python level4.py < test.txt";
	FILE *fp;
	int i;
	char *pos_pw_list[100] = {"8c86", "7692", "a519", "3e61", "7dd6", "8919", "aaea", "f34b", "d9a2", "39f7", "626b", "dc78", "2a98", "7a85", "cd15", "80fa", "8571", "2f8a", "2ca6", "7e6b", "9c52", "7423", "a42c", "7da0", "95ab", "7de8", "6537", "ba1e", "4fd4", "20a0", "8a28", "2801", "2c9a", "4eb1", "22a5", "c07b", "1f39", "72bd", "97e9", "affc", "4e41", "d039", "5d30", "d13f", "c264", "c8be", "2221", "37ea", "ca5f", "fa6b", "5ada", "607a", "e469", "5681", "e0a4", "60aa", "d8f8", "8f35", "9474", "be73", "ef80", "ea43", "9f9e", "77d7", "d766", "55a0", "dc2d", "a970", "df5d", "e747", "dc69", "cc89", "e59a", "4f68", "14ff", "7928", "36b9", "eac6", "5c87", "da48", "5c1d", "9f63", "8b30", "5534", "2434", "4a82", "d72c", "9b6b", "73c5", "1bcf", "c739", "6c31", "e138", "9e77", "ace1", "2ede", "32e0", "3694", "fc92", "a7e2"};
	fp = fopen("test.txt", "w+");
  for(i = 0; i < 100; i++){
		fseek(fp, 0L, SEEK_SET);
		printf("Trying password: %s\n", pos_pw_list[i]);
		fprintf(fp, pos_pw_list[i]);
		system(str);
	}
  fclose(fp);
}
```
Probably could be done far simpler in python, but I love and know C best, so there it is.

After running my C script I got the key:

>Please enter correct password for flag: That password is incorrect
>
>Trying password: e469
>
>Please enter correct password for flag: Welcome back... your flag, user:
>
>picoCTF{fl45h_5pr1ng1ng_d770d48c}
