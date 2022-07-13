---
description: >-
  Bandit is one of the wargames category created by OverTheWire community
  available at https://overthewire.org/wargames/. I decided to use Kali Linux
  for this wargame.
cover: https://www.slashfilm.com/img/gallery/wargames-reboot-teaser/intro-import.webp
coverY: 0
---

# 💻 Bandit OverTheWire

### Bandit 0

![](<.gitbook/assets/image (10).png>)

For the this level, it wants us to connect to a host using SSH. SSH is a network protocol used to connect into another remote device. The details of the host is as below:

* host: bandit.labs.overthewire.org
* port: 2220
* username: bandit0
* password: bandit0

From these information we can use SSH which was already provided in Linux distribution to connect to the host with command `ssh bandit0@bandit.labs.overthewire.org -p 2220` then enter bandit0 as the password. We will be welcomed with OverTheWire page.

![](<.gitbook/assets/image (182).png>)

### Bandit 0-1

![](<.gitbook/assets/image (161).png>)

The first level wants us to find a readme file and log into bandit1 using SSH. We use **ls** command  the files in the bandit0 directory and use **cat** or **strings** command on the readme file to get the content of the file which is the password for bandit2.

![](<.gitbook/assets/image (233).png>)

### Bandit 1-2

![](<.gitbook/assets/image (34).png>)

In Bandit 1-2, it wants us to read the content of a file with dash "**-**" as the filename. We cannot directly cat or strings the file as **-** is an argument that refers to the dev/stdin or dev/stdnout which is a [stream that are established when a Linux command is executed.](https://www.howtogeek.com/435903/what-are-stdin-stdout-and-stderr-on-linux/) To open file with dash "-" as the filename, we need to specify the full location using ** `/.`**

![](<.gitbook/assets/image (144).png>)

### Bandit 2-3

![](<.gitbook/assets/image (154).png>)

In Bandit 3, the challenge asks us to read the content of file called "spaces in this filename". To read any file with spaces, we need to include backslash "\\" after each word .

![](<.gitbook/assets/image (40).png>)

### Bandit 3-4

![](<.gitbook/assets/image (255).png>)

Bandit 3-4 ask us to read the content of a file that is hidden in the inhere directory. We can use `ls -la` to display every file in the directory including file starting with .

![](<.gitbook/assets/image (177).png>)

![](<.gitbook/assets/image (238).png>)

### Bandit 4-5

![](<.gitbook/assets/image (39).png>)

This challenge ask us to read the only human readable file in the inhere directory. We can use `strings` command to do this. Since there are multiple file in the directory we can combine `strings` with `*` symbol. `*`  is a symbol that stands for everything linux distribution.

![](<.gitbook/assets/image (256).png>)

### Bandit 5-6

![](<.gitbook/assets/image (3).png>)

In Bandit 5-6, the challenge ask us to read the content of a file with a specific details including:

* human readable
* 1033 byte
* not executable

We can use the `find` command with option `-type` and `-size` to specify the details of the file. You can read more about any command in Linux from the [manpages](https://man7.org/linux/man-pages/man1/find.1.html) with command `man find.` Type f stands file and size 1033c stands for 1033 bytes.

![](<.gitbook/assets/image (30).png>)

### Bandit 6-7

![](<.gitbook/assets/image (190).png>)

In Bandit 6-7 the challenge as us to find a file with these details:

* can be anywhere on host device
* owned by use bandit7
* owned by group bandit6
* 33 bytes size

We can also use `find` command with different option for this challenge. Option `-user` and `-group` is used to specify which user the file is owned by. We use command `find` in `/` since it is the root of all directory.&#x20;

![](<.gitbook/assets/image (204).png>)

There are lots of directory that does not allow bandit6 `user` to open or scan the directory, however from all of the search result, we have one file that fit all the description.

![](<.gitbook/assets/image (9).png>)

### Bandit 7-8

![](<.gitbook/assets/image (57).png>)

In bandit 7-8 the challenge ask us to find the password in a file called data.txt. The detail of the password is it is next to the word millionth. We can use the [`grep`](https://linuxcommand.org/lc3\_man\_pages/grep1.html) command to find the word millionth in the file.

![](<.gitbook/assets/image (136).png>)

### Bandit 8-9

![](<.gitbook/assets/image (240).png>)

Bandit 8-9 challenge ask us to find the password in a file called data.txt. The password is the only line of text that occurs only once in the file. We can use cat and pipe it with sort and uniq command to get the password.&#x20;

[Sort](https://man7.org/linux/man-pages/man1/sort.1.html) command is used to arrange the record of a file in a particular order so that the repeating line is sorted together while [uniq](https://www.geeksforgeeks.org/uniq-command-in-linux-with-examples/) command with option -u is used to print the only non repeating line in the file. The full command is `cat data.txt|sort|uniq -u` .

![](<.gitbook/assets/image (115).png>)

### Bandit 9-10

![](<.gitbook/assets/image (90).png>)

In bandit 9-10, the challenge ask us to find the password in data.txt with these details:

* human readable
* starts with = characters

From these details we can use the strings command to list out the readable strings and pipe it with grep to take out the strings starting with =.

![](<.gitbook/assets/image (65).png>)

### Bandit 10-11

![](<.gitbook/assets/image (72).png>)

In Bandit 10-11 it asks us to read a base64 encoded file. Base64 is a binary to ASCII encoding scheme that is used to obfuscate, hash data etc. A base64 encoded data will usually end with ==. We can use the base64 decoding tools in kali linux distribution to decode the file with cat and pipe it with base64 decoder. `cat data.txt | base64 -d.`

![](<.gitbook/assets/image (216).png>)

### Bandit 11-12

![](<.gitbook/assets/image (167).png>)

For bandit 11-12 the challenge asks us to decode a file which has been rotated by 13 positions. This encoding is also known as [Rot13](https://en.wikipedia.org/wiki/ROT13). To put it simply, ROT 13 is a substitution cipher that works by offset the alphabet by 13 places.

*   Encode: &#x20;

    ```
    tr 'A-Za-z' 'N-ZA-Mn-za-m'
    ```
*   Decode:&#x20;

    ```
    tr 'N-ZA-Mn-za-m' 'A-Za-z'
    ```

![](<.gitbook/assets/image (200).png>)

### Bandit 12-13

![](<.gitbook/assets/image (66).png>)

For Bandit 12-13, the password is stored in the file data.txt which is a hexdump of file that has been compressed repeatedly. Hexdump is a hexadecimal view of computer data. The details of the file is as below:

* Hexdump data&#x20;
* Repeatedly compressed

![](<.gitbook/assets/image (264).png>)

To change and work on the file, we need to move it somewhere we have permission to such as /tmp. After creating a new directory in tmp using mkdir, we can copy the file into the directory and start working on it. First, we can use [xxd ](https://linux.die.net/man/1/xxd)to reverse the hexdump file to its original binary. Then, using file command we can figure out the type of file. It seems the original file is called data2.bin which is a gzip compressed data.

![](<.gitbook/assets/image (112).png>)

We can use bzip2 to deflate the gzip compression. We do this process for two more time till we get the data4 file which is a tar archive. To deflate tar archive files, we can use tar xvf.&#x20;

![](<.gitbook/assets/image (43).png>)

After repeatedly deflating more files, we finally get data8 file which is the original file with password.

![](<.gitbook/assets/image (209).png>)

### Bandit 13-14

![](<.gitbook/assets/image (14).png>)

For bandit 13-14 the challenge asks us to log into the SSH using a private SSH key. From the SSH manpage, we can use -i option to use the private key and connect to the server.

![](<.gitbook/assets/image (110).png>)

The full command is `ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220/`

![](<.gitbook/assets/image (207).png>)

Then we can cat the password in /etc/bandit\_pass/bandit14.

![](<.gitbook/assets/image (159).png>)

### Bandit 14-15

![](<.gitbook/assets/image (7).png>)

For bandit 14-15, the challenge wants us to submit the password of current level to port 30000 on localhost(bandit14). To do this we can use [netcat](https://en.wikipedia.org/wiki/Netcat), a tool to read and writes data using tcp or udp protocol, it is also used for port listening. It works by creating a socket from server to client, once connected, the client and server can send data to each other. To use netcat in linux we use the nc command, `nc localhost 30000`.

![](<.gitbook/assets/image (48).png>)

### Bandit 15-16

![](<.gitbook/assets/image (19).png>)

For bandit 15-16, the challenge wants us to submit the password of current level to port 30001 using ssl encryption. We can use [OpenSSL](https://en.wikipedia.org/wiki/OpenSSL), a cryptography library that offers open-source application of the TLS protocol for this process. From the [man page](https://linux.die.net/man/1/openssl), we can use option s\_client to establish a ssl/tls encryption and option -connect to specify the target and port.&#x20;

![](<.gitbook/assets/image (205).png>)

After the connection is established, we can enter the password for current level to get the password.

![](<.gitbook/assets/image (28).png>)

### Bandit 16-17

![](<.gitbook/assets/image (164).png>)

Fort bandit 16-17 the challenge wants us to submit the password for current level to a port on localhost. The details of the port are:

* between 31000 to 32000
* uses SSL&#x20;
* will reply with credentials&#x20;

To scan for the active port between 31000 to 32000, we can use [nmap](https://nmap.org/) a powerful port scanning tool. We can specify the range of port we wanted to scan using -p option.

![](<.gitbook/assets/image (195).png>)

From the results, we get six active port. To figure out which one uses ssl, we can use OpenSSL the same way from the previous level. Keep trying to connect onto all the port to find out which one will give us the credentials.

![](<.gitbook/assets/image (214).png>)

Finally on the port 31790 we finally get a port that uses ssl encryption. After submitting the password for the current level to the port, the server will reply with a ssh private key for the next level.

![](<.gitbook/assets/image (180).png>)

### Bandit 17-18

![](<.gitbook/assets/image (116).png>)

Fort bandit 17-18 it wants us to find a the only line that has been changed between two files, passwords.old and passwords.new. We can use command diff, to compare both files and find the differences and get the password.

![](<.gitbook/assets/image (151).png>)

### Bandit 18-19

![](<.gitbook/assets/image (267).png>)

This is the first challenge that took me a while to get through. So whenever we start a bash shell, a .bashrc file will be run on that shell. For this challenge, the .bashrc file has been modified to log us out whenever we tried to login meaning we wont be able to cat the readme file.

![](<.gitbook/assets/image (125).png>)

The first thing I thought is to login as bandit17 and try to modify the .bashrc file in bandit18 home directory. However,  the file can only be read or write by user bandit19.

![](<.gitbook/assets/image (248).png>)

Then I googled ".bashrc prevent from login" and found a similar question on [serverfault.com](https://serverfault.com/questions/94503/login-without-running-bash-profile-or-bashrc). From this forum it seems that we can avoid using bash shell through:

* using ssh -t option and /bin/sh, this option will spawn a pseudo-terminal shell instead of an interactive shell. There are a couple different shell provided in a linux distributon and /bin/sh is one of them. By using -t and /bin/sh we will avoid spawning the bash shell and thus will not use the .bashrc configuration.

![](<.gitbook/assets/image (140).png>)

From here, we will get a simple but still interactive sh shell and cat the passsword.

![](<.gitbook/assets/image (8).png>)

### Bandit 19-20

![](<.gitbook/assets/image (203).png>)

For bandit 19-20 it taught us about the setuid or also known as set user id. By invoking an executable setuid, we gain the priviledge of another user. In this challenge, we were able to gain the priviledge of user bandit20 and read the password through the setuid.

![](<.gitbook/assets/image (193).png>)

### Bandit 20-21

![](<.gitbook/assets/image (82).png>)

For bandit 20-21, it gave us an executable setuid that does these:

* makes a connection to localhost port that we specify
* read a line of text from the port and compares it to previous password
* if the password is correct, it replies the password for next level

From my understanding this is what we need to do in order to get the password:

1. Use netcat to listen to a port on localhost
2. Enter the previous password&#x20;
3. On another screen in the same ssh session, execute the setuid to the port

The only problem I have is not knowing how to have different shell or screen in the same ssh session. From this [post ](https://askubuntu.com/questions/332104/open-another-terminal-window-with-the-same-ssh-session-as-original-window)I find out that there are several ways to do this including using screen, tmux and gnome-terminal. First, I typed tmux and open another shell. Now, using the main shell, I can listen to a port on localhost with command `nc -l localhost -p 1111.`

![](<.gitbook/assets/image (178).png>)

Then, I press `Ctrl + A` to go to tmux shell and execute the setuid to port 1111.

![](<.gitbook/assets/image (63).png>)

Going back to the main shell, I can see the password fo the next level.

![](<.gitbook/assets/image (170).png>)

### Bandit 21-22

![](<.gitbook/assets/image (35).png>)

Bandit 21-22 taught us about cron, a tool to schedule job at specific times. By going to /etc/cron.d/ we were able to find cronjob for user bandit22. This is what the cronjob does:

* Every time bandit22 reboot, it will execute a script from /usr/bin/cronjob\_bandit22.sh and then send it to /dev/null to discard it.

The script simply gives permission to other user to only read the file /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv, the password for bandit22 has also been copied to the file.

![](<.gitbook/assets/image (24).png>)

We can gain the password by using cat on the file.

![](<.gitbook/assets/image (97).png>)

### Bandit 22-23

![](<.gitbook/assets/image (51).png>)

For bandit 22-23, it ask us to do same thing as the previous level. Using cat on the cron script for bandit23 we can see the code for the script.

![](<.gitbook/assets/image (252).png>)

This is what the script does:

1. Initialize $myname variable which is whatever the whoami output is for the user.
2. Second variable($mytarget) is the output of md5sum and cut of command `echo I am user bandit23`.
3. Lastly, it copies the password for bandit23 to file /tmp/$mytarget.

So now we just need to redo the command to get the value of $mytarget variable. The output of the command will be the filename that kept the password for the next level.

![](<.gitbook/assets/image (88).png>)

### Bandit 23-24

![](<.gitbook/assets/image (122).png>)

Bandit 23-24 is a challenge that test our understanding from the previous levels and the logic behind a code or script. As the previous level, we can cat the cronjob script for bandit24 and try to understand what it does.

![](<.gitbook/assets/image (187).png>)

From my understanding this is what the script does:

1. Initialize $myname variable(bandit23).
2. If the owner of the file is bandit23, it will e**xecutes** and delete all files in /var/spool/bandit23.
3. This process happens every 60 second.

Since the script will first **executes** with permission of user bandit24  before deleting them, we can create a script that cat the password in /tmp/bandit\_pass/bandit24 and save it into a writable file in  /tmp/. So first we create a directory in /tmp/, then we create an empty file called pass.txt. Lastly, we changed the permission of the file so that it can be read or write by anyone using chmod 777.

![](<.gitbook/assets/image (46).png>)

Then we cd to /var/spool/bandit24 and create a script in there. Make sure to change the permission of the script so anyone can read or write it using chmod 777. Since the file in this folder is deleted every 60s, we might have to do it a couple times to ensure we can change the permission before it is deleted.

![](<.gitbook/assets/image (60).png>)

What the script does is it cat the file /etc/bandit\_pass/bandit24 and save the output tothe file we created previously in /tmp/asylumdx/pass.txt.&#x20;

![](<.gitbook/assets/image (61).png>)

Now we can see whether the cronjob script has executed the script by checking if the script.sh file is still in the directory. When we see the file has been deleted, we should be able to see the password in /tmp/asylumdxs/pass.txt.

![](<.gitbook/assets/image (113).png>)

<mark style="color:red;">Some notes for myself</mark>: I wasnt aware that the cronjob script needed permission in order for them to execute the script and write to the pass.txt file. It took me some googling on "kali cronjob script not working" till I find an answer in [stackoverflow forum](https://stackoverflow.com/questions/22743548/cronjob-not-running).

### Bandit 24-25

![](<.gitbook/assets/image (32).png>)

Bandit 24-25 asks us to brute force the pincode alongside the password for bandit24 and submit it port 30002. We can create a bash script for this task.

