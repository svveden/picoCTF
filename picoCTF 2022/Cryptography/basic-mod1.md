## Description

>We found this weird message being passed around on the servers, we think we have a working decrpytion scheme. Download the message here. Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore. Wrap your decrypted message in the picoCTF flag format (i.e. picoCTF{decrypted_message})

The given encrypted text is:

>54 211 168 309 262 110 272 73 54 137 131 383 188 332 39 396 370 182 328 327 366 70 

I wrote a simple C program with a switch case that converts the mod 37 of each number to their corresponding codes.

```
#include <stdio.h>

int main(void){
	int ans;
	int a[] = {54, 211, 168, 309, 262, 110, 272, 73, 54, 137, 131, 383, 188, 332, 39, 396, 370, 182, 328, 327, 366, 70};
	enum answer{}
	for(int i = 0; i < (sizeof(a)/sizeof(a[0])); i++){
		ans = a[i]%37;
		switch(ans){
			case 0: printf("a");
			break;
			case 1: printf("b");
			break;
			case 2: printf("c");
			break;
			case 3: printf("d");
			break;
			case 4: printf("e");
			break;
			case 5: printf("f");
			break;
			case 6: printf("g");
			break;
			case 7: printf("h");
			break;
			case 8: printf("i");
			break;
			case 9: printf("j");
			break;
			case 10: printf("k");
			break;
			case 11: printf("l");
			break;
			case 12: printf("m");
			break;
			case 13: printf("n");
			break;
			case 14: printf("o");
			break;
			case 15: printf("p");
			break;
			case 16: printf("q");
			break;
			case 17: printf("r");
			break;
			case 18: printf("s");
			break;
			case 19: printf("t");
			break;
			case 20: printf("u");
			break;
			case 21: printf("v");
			break;
			case 22: printf("w");
			break;
			case 23: printf("x");
			break;
			case 24: printf("y");
			break;
			case 25: printf("z");
			break;
			case 26: printf("0");
			break;
			case 27: printf("1");
			break;
			case 28: printf("2");
			break;
			case 29: printf("3");
			break;
			case 30: printf("4");
			break;
			case 31: printf("5");
			break;
			case 32: printf("6");
			break;
			case 33: printf("7");
			break;
			case 34: printf("8");
			break;
			case 35: printf("9");
			break;
			case 36: printf("_");
			break;


		}
	}
	return 0;
}
```
After running it, I got the code: picoCTF{r0und_n_r0und_c0a86577}
