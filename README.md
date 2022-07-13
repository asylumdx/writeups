---
description: >-
  On 16th mac - 31th mac I participated in the picoctf 2021 competition as a
  solo player. Here's some of my writeup for the challenges. Overall, I finished
  on 348th / 6200 teams.
---

# Pico CTF 2021 Writeups

![](<.gitbook/assets/image (117) (1).png>)

![](<.gitbook/assets/image (118) (1).png>)

## **W**eb Exploitation

### Ancient History

![](<.gitbook/assets/Screenshot\_3 (7).png>)

We were given a website

![](<.gitbook/assets/Screenshot\_1 (11).png>)

After viewing the source

![](<.gitbook/assets/Screenshot\_2 (8).png>)

Found the flag amongst the obfuscated code. **picoCTF{th4ts\_k1nd4\_n34t\_3bed1170}**

### GET aHEAD

![](.gitbook/assets/ah1.png)

We were given a website

![](.gitbook/assets/ah2.png)

Based on the challenge title, we should try get the website header either using curl or Burpsuite. curl command : `curl -X HEAD -i` [`http://mercury.picoctf.net:47967/`](http://mercury.picoctf.net:47967)\`\`

![](<.gitbook/assets/image (14) (1).png>)

and we got the flag from the header. **picoCTF{r3j3ct\_th3\_du4l1ty\_cca66bd3}**

### Cookies

![](<.gitbook/assets/image (15) (1).png>)

![](<.gitbook/assets/image (16) (1).png>)

The title and hint of the website talks about cookies, lets view the cookies using the in browser function.

![](<.gitbook/assets/image (18) (1).png>)

The current cookie value is -1, lets try changing it to 1and see if we get any output.

![](<.gitbook/assets/image (19) (1).png>)

Based on the output, we need to traverse and try different value of cookies to get the flag.

![](<.gitbook/assets/image (20) (1).png>)

And we got the flag on the 18 cookies. **picoCTF{3v3ry1\_l0v3s\_c00k135\_064663be}**

### Scavenger Hunt

![](<.gitbook/assets/image (22) (1).png>)

![](<.gitbook/assets/image (23).png>)

Seems like a normal html website, lets take a look at the source.

![](<.gitbook/assets/image (24) (1).png>)

It seems that this is a directory traversing challenge, we got the first part picoCTF{t from the source. It says the website was made from html,css and js. Lets take a look at those.

![](<.gitbook/assets/image (27) (1).png>)

Second part: h4ts\_4\_10

![](<.gitbook/assets/image (25) (1).png>)

We found a js script, lets open it.

![](<.gitbook/assets/image (26) (1).png>)

From the hint, we can guess the next part is in robots.txt that is used to configure crawler from accessing certain directory of the website.

![](<.gitbook/assets/image (28) (1).png>)

3rd part: t\_0f\_pl4c

![](<.gitbook/assets/image (29) (1).png>)

4th part: 3s\_2\_100k

![](<.gitbook/assets/image (30) (1).png>)

5th part: \_f7ce8828} . flag: **picoCTF{th4ts\_4\_10t\_0f\_pl4c3s\_2\_100k\_f7ce8828}**

### Who are you?

![](<.gitbook/assets/image (31) (1).png>)

![](<.gitbook/assets/image (33) (1).png>)

Opening the website told us that we can only access it with picobrowser. From reading past writeup, it seems that we need to change the user agent to access it. We use the curl command : `curl -A "PicoBrowser" http://mercury.picoctf.net:46199` to change the user agent.

![](<.gitbook/assets/image (34) (1).png>)

From the website, it asks us to visit the website, from the website itself. We can use curl command : `curl -A "PicoBrowser" http://mercury.picoctf.net:46199/ -H "Referer: http://mercury.picoctf.net:46199"`

![](<.gitbook/assets/image (35) (1).png>)

Next it asks us to access the website from 2018. We can modify the time header through: `curl -A "PicoBrowser" http://mercury.picoctf.net:46199/ -H "Referer: http://mercury.picoctf.net:46199" -H "Date: Wed 17 Mar 2018 02:47:59 GMT"`

![](<.gitbook/assets/image (36) (1).png>)

Now it asks us to send request without being tracked. We can use the DNT(Do Not Track) header curl command: `curl -A "PicoBrowser" http://mercury.picoctf.net:46199/ -H "Referer: http://mercury.picoctf.net:46199" -H "Date: Wed 17 Mar 2018 02:47:59 GMT" -H "DNT: 1"`

![](<.gitbook/assets/image (37) (1).png>)

Now it only allows people from Sweden. We just need to use a sweden ip and X-Forwarded-For header to foward our curl request ip. `curl -A "PicoBrowser" http://mercury.picoctf.net:46199/ -H "Referer: http://mercury.picoctf.net:46199" -H "Date: Wed 17 Mar 2018 02:47:59 GMT" -H "DNT: 1" -H "X-Forwarded-For:193.150.233.115"`

![](<.gitbook/assets/image (38) (1).png>)

Now it also want us to speak in Sweden. We just need to change the language header using the syntax: `curl -A "PicoBrowser" http://mercury.picoctf.net:46199/ -H "Referer: http://mercury.picoctf.net:46199" -H "Date: Wed 17 Mar 2018 02:47:59 GMT" -H "DNT: 1" -H "X-Forwarded-For:193.150.233.115" -H 'Accept-LAnguage: sv'`

![](<.gitbook/assets/image (39) (1).png>)

And we finally got the flag. **picoCTF{http\_h34d3rs\_v3ry\_c0Ol\_much\_w0w\_8d5d8d77}**

### Some Assembly Required 1

![](<.gitbook/assets/image (40).png>)

![](<.gitbook/assets/image (41) (1).png>)

This challenge is straight forward. We just need to look for the wasm files in the debugger browser function to get the flag. **picoCTF{8857462f9e30faae4d037e5e25fee1ce}**

### It is my birthday

![](<.gitbook/assets/image (42).png>)

This challenge is about the md5 hash collision that makes it unsecure.

![](<.gitbook/assets/image (43) (1).png>)

The website requires us to upload two different pdf files with the same hashes. It also has an upload limit not allowing for more than 100kbs files. By using this [website](https://www.mscs.dal.ca/\~selinger/md5collision/), we got two exe program with md5 hash collision.

![](<.gitbook/assets/image (44) (1).png>)

Now since the php script only requires the uploaded files to have .pdf extension, we can just rename the files and add .pdf before uploading it.

![](<.gitbook/assets/image (45) (1).png>)

![](<.gitbook/assets/image (46) (1).png>)

And we got the flag. **picoCTF{c0ngr4ts\_u\_r\_1nv1t3d\_73b0c8ad}**

### Most cookies

![](<.gitbook/assets/image (48) (1).png>)

This challenge is about cookie forging. We were given a website and the server source code.

![](<.gitbook/assets/image (49) (1).png>)

From the challenge description, we know that the website uses flask cookies. Flask cookie was made by using a 'secret key' to ensure it's secure. Let's see the value of the cookie using [flask-unsign](https://github.com/Paradoxis/Flask-Unsign).

![](<.gitbook/assets/image (50) (1).png>)

Here we can see that the value is blank. However from the source code server.py, we can see that in order to get the flag, we need to set it to admin.

![](<.gitbook/assets/image (51) (1).png>)

Before continue to forge it, we need to find the secret key of the flask cookie.

![](<.gitbook/assets/image (52) (1).png>)

Here we can see that the secret key is chosen randomly from a list. We can bruteforce the wordlist by using [`flask-unsign`](https://github.com/Paradoxis/Flask-Unsign) feature.

![](<.gitbook/assets/image (53).png>)

![](<.gitbook/assets/image (54) (1).png>)

From the bruteforce, we found out the secret key is butter. Now we can forge a new cookie with value:admin and secret key: butter.

![](<.gitbook/assets/image (55).png>)

Now change the cookie value on the browser to get the flag.

![](<.gitbook/assets/image (56).png>)

flag: **picoCTF{pwn\_4ll\_th3\_cook1E5\_743c20eb}**

## Cryptography

### Pixelated

![](.gitbook/assets/Pixelated.png)

For this challenge we were given two images that seems to be made out of statics.

![1st image](.gitbook/assets/scrambled1.png)

![2nd image](.gitbook/assets/scrambled2.png)

I treated this challenge as steganography and used [StegSolve](https://github.com/eugenekolo/sec-tools/tree/master/stego/stegsolve) to combine both images to produce an output.

![](.gitbook/assets/Screenshot\_1.png)

After combining both and using the ADD function we can see the flag **picoCTF{0542dc1d).**

### Mod 26

![](<.gitbook/assets/image (57) (1).png>)

It's a simple rot13 encryption. Let's use [CyberChef](https://gchq.github.io/CyberChef/#recipe=ROT13\(true,true,false,13\)\&input=Y3ZwYlBHU3thcmtnX2d2enJfVid5eV9nZWxfMl9lYmhhcWZfYnNfZWJnMTNfR1lwWE9IcVh9) to decrypt it.

![](<.gitbook/assets/image (58) (1).png>)

flag: **picoCTF{next\_time\_I'll\_try\_2\_rounds\_of\_rot13\_TLcKBUdK}**

### Mind you Ps and Qs

![](<.gitbook/assets/image (59).png>)

It's is the usual RSA challenge.

![](<.gitbook/assets/image (60) (1).png>)

We have to decrypt it based on the value given. I'm not good at math and just use[ rsactftool](https://github.com/Ganapati/RsaCtfTool) to decrypt it.

![](<.gitbook/assets/image (61) (1).png>)

flag: **picoCTF{sma11\_N\_n0\_g0od\_23540368}**

### Dacshund Attacks

![](<.gitbook/assets/image (62) (1).png>)

![](<.gitbook/assets/image (63).png>)

In this challenge we were given e,n and c value. The d value can be calculated by yourself. Based on the challenge we know that d has a small value meaning it is vulnerable to the[ wiener attack](https://en.wikipedia.org/wiki/Wiener's\_attack). We can use rsactftool again to decrypt it.

![](<.gitbook/assets/image (64) (1).png>)

Flag: **picoCTF{proving\_wiener\_1146084}**

### Play Nice

![](<.gitbook/assets/image (65) (1).png>)

![](<.gitbook/assets/image (66) (1).png>)

This is just a playfair cipher. We can use [https://www.dcode.fr/playfair-cipher](https://www.dcode.fr/playfair-cipher) to decrypt it.

![](<.gitbook/assets/image (67) (1).png>)

Enter the plaintext into netcat.

![](<.gitbook/assets/image (68) (1).png>)

flag: **picoCTF{2e71b99fd3d07af3808f8dff2652ae0e}**

## Reverse Engineering

### Transformation

![](<.gitbook/assets/image (97) (1).png>)

![](<.gitbook/assets/image (98) (1).png>)

Opening the file, it looks some kind of unicode characters. I proceed to use [CyberChef](https://gchq.github.io/CyberChef) magic feature to see if it can decrypt it. By putting picoCTF in the crib, we were able to decode it.

![](<.gitbook/assets/image (99) (1).png>)

**picoCTF{16\_bits\_inst34d\_of\_8\_26684c20}**

### keygenme-py

![](<.gitbook/assets/image (100).png>)

![](<.gitbook/assets/image (101) (1).png>)

Looking at the source code, we only need to find the key\_part\_dynamic\_1trial part of the flag.

![](<.gitbook/assets/image (102).png>)

Looking at the source, we can see that the dynamic key is taken from the certain value of hexdigest of the username which is GOUGH. We can write a short python script to print it.

![](<.gitbook/assets/image (103) (1).png>)

The full flag: **picoCTF{1n7h3|<3y\_of\_f911a486}**

### crackme

![](<.gitbook/assets/image (104).png>)

![](<.gitbook/assets/image (105).png>)

From the source code, we can see the the program uses ROT47 to encode and decode their bezos\_cc\_secret. We can use [CyberChef](https://gchq.github.io/CyberChef) to decode it.

![](<.gitbook/assets/image (106).png>)

Flag: **picoCTF{1|\\/|\_4\_p34||ut\_4593da8a}.**

### speeds and feeds

![](<.gitbook/assets/image (107).png>)

Lets use netcat and save the output.

![](<.gitbook/assets/image (108).png>)

![](<.gitbook/assets/image (109) (1).png>)

From the hint, we know that it is from[ CNC machine](https://www.steckermachine.com/blog/g-code-m-code) which uses G-code as the programming language. After some googling, I found this [https://ncviewer.com/](https://ncviewer.com) which can be used to plot the G-code language.

![](<.gitbook/assets/image (110) (1).png>)

flag: **picoCTF{num3r1cal\_c0ntr0l\_f3fea95b}.**

### Shop

![](<.gitbook/assets/image (111) (1).png>)

![](<.gitbook/assets/image (112) (1).png>)

In this challenge, we have to exploit the fact that there the programmer did not implement any edge cases in the coin system of the market. We can input any value into the coin such as negative to exploit it.

![](<.gitbook/assets/image (113) (1).png>)

The flag is encrypted with ascii. Decode it using [https://convert.town/ascii-to-text](https://convert.town/ascii-to-text).

![](<.gitbook/assets/image (114) (1).png>)

Flag: **picoCTF{b4d\_brogrammer\_797b292c}**.

## Forensics

### Information

![](<.gitbook/assets/Screenshot\_4 (1).png>)

In this challenge we were given an image and the hint says something regarding information.

![](.gitbook/assets/cat.jpg)

So I just try to see the metadata of the image using exiftool.

![](<.gitbook/assets/Screenshot\_2 (1).png>)

Looking at the license data, it looks like a base 64 string. Lets try decrypting it with [CyberChef](https://gchq.github.io/CyberChef).

![](<.gitbook/assets/Screenshot\_3 (1).png>)

And we got the flag **picoCTF{the\_m3tadatais\_modified}.**

### Weird File

![](.gitbook/assets/Screenshot\_5.png)

In this challenge we were given a Word document with a hint that there are some shell or macro in the file.

![](<.gitbook/assets/Screenshot\_1 (4).png>)

We're also given a youtube [video ](https://www.youtube.com/watch?v=Y7IJjnLGqTQ)that talks about macros in docx file. In the video it shows that we can use[ olevba](https://github.com/decalage2/oletools/wiki/olevba) to extract macros source code from word and ppt files.

![](<.gitbook/assets/Screenshot\_1 (1).png>)

From the extracted macros source, we can see that the embedded script is trying to print a line of strings that seems to be encoded in base 64.

```
$ echo cGljb0NURnttNGNyMHNfcl9kNG5nM3IwdXN9 | base64 -d                                                        1 ⨯
picoCTF{m4cr0s_r_d4ng3r0us}                                                                                                                     
```

After decoding it, we got the flag **picoCTF{m4cr0s\_r\_d4ng3r0us}**.

### Matryoshka doll

![](<.gitbook/assets/Screenshot\_3 (2).png>)

This is matryoshka doll challenge in which we have to extract data from image multiple times to get the flag.

![](.gitbook/assets/dolls\(1\).jpg)

So lets binwalk the image to extract the data a couple times.

![](<.gitbook/assets/Screenshot\_2 (2).png>)

After a couple times we got the flag.

![](<.gitbook/assets/Screenshot\_4 (2).png>)

**picoCTF{336cfd51c9d9774fd37196c1d7320ff}.**

### Wireshark doo dooo do doo...

![](<.gitbook/assets/Screenshot\_5 (1).png>)

In this challenge we were given a pcap file, lets open it with wireshark.

![](<.gitbook/assets/Screenshot\_1 (5).png>)

I didnt find anything by trying to follow the packet so next I try to export the objects from the pcap.

![](<.gitbook/assets/Screenshot\_2 (3).png>)

Then, I tried opening some of the files and found a string that seems like it has been encoded with Caesar Cipher.

![](<.gitbook/assets/image (1) (1).png>)

So we can try decoding it either using some website such as [dcode.fr ](https://www.dcode.fr)or using python script from [github](https://github.com/rhamaa/Caesar-Cipher-Brute-Force/blob/master/caesar\_brute.py):

![](<.gitbook/assets/image (5) (1).png>)

The flag is **picoCTF{p33kab00\_**_**1\_s33\_u\_deadbeef}**._

### Macrohard WeakEdge

![](.gitbook/assets/Screenshot\_6.png)

At first I thought this challenge was similar to weird file and tried to extract macro data from the file using olevba, however I didnt manage to get any useable output from it.

![](<.gitbook/assets/Screenshot\_4 (4).png>)

Then I remembered that ppt files are just made up from a bunch of files. I performed binwalk on it to extract the data.

![](<.gitbook/assets/Screenshot\_1 (8).png>)

And after scouring around in the files, I manages to get a string that looks like it has been encoded.

![](<.gitbook/assets/Screenshot\_2 (6).png>)

Since caesar cipher didn't work, I just put the strings into CyberChef and it automatically detected that it was from base64 and got the flag.

![](<.gitbook/assets/Screenshot\_3 (5).png>)

flag: **picoCTF{D1d\_u\_kn0w\_ppts\_r\_z1p5}**

### Trivial Flag Transfer Protocol

![](<.gitbook/assets/Screenshot\_5 (3).png>)

In this challenge we have to work with a pcap file. The title says something about ftp. As usual lets try opening it in wireshark and export the ftp objects from the pcap.

![](<.gitbook/assets/Screenshot\_1 (9).png>)

We manages to get 2 strings files and 3 pictures.

![](<.gitbook/assets/image (7) (1).png>)

Seems like it is encoded with caesar cipher. After decoding it, the instruction says:

> TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN

and the plan:

> IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS

After that, lets open the program.deb

![](<.gitbook/assets/Screenshot\_3 (6).png>)

It seems that one of the image contains a hidden flag and they used [steghide](https://github.com/StefanoDeVuono/steghide) to hid it with the key:DUEDILIGENCE.

![](<.gitbook/assets/image (9).png>)

After trying steghide on all 3 pictures, we finally get an output on the third image.

![](<.gitbook/assets/image (10) (1).png>)

flag: **picoCTF{h1dd3n\_1n\_pLa1n\_51GHT\_18375919}**

### Wireshark two twooo two twoo ..

![](<.gitbook/assets/image (12) (1).png>)

This challenge was quite guessy and time consuming. We were given a pcap file. However after trying the usual follow packets and export objects, I only found fake flags. I saw someone mentions using NetworkMiner in the discord server and tried it.

![](.gitbook/assets/1.png)

After some times of taking a look at how it categorize each packets, I noticed something weird at the server and ip ttl value of some packets.

![](.gitbook/assets/7.png)

I then tried following one of the packets and it gave a website: [http://reddshrimpandherring.com/](http://reddshrimpandherring.com) brought me to a website that give something like a flag.

![](.gitbook/assets/3.png)

However after decoding it to base64 and submitting, it seems that it was a fake flag such as suggested by the site name itself.

![](.gitbook/assets/sa.png)

Then I take a look back at the packets and notice that before the website, each of the packets have a different strings that looks like a base64 encoded strings. I then tried to decode one of the strings.

![](.gitbook/assets/6.png)

And indeed it produce part of the flag.

![](.gitbook/assets/9.png)

After collecting all of the strings from the packets, we got the flag. **picoCTF{dns\_3xf1l\_ftw\_deadbeef}.**

### Disk, Disk sleuth! II

![](.gitbook/assets/Screenshot\_4.png)

The challenge gave us an image that can be mounted with a hint that the flag is stored a file called 'down-at-the-bottom.txt'. Rather than using sleuthkit as suggested, I just use binwalk to extract all the files in the image and find the file with the flag manually.

![](.gitbook/assets/Screenshot\_2.png)

![](.gitbook/assets/Screenshot\_3.png)

Manages to found the flag file in the root directory. The flag is **picoCTF{f0r3ns1c4t0rn0v1c30ba8d02d}.**

### Milkslap

![](<.gitbook/assets/Screenshot\_3 (4).png>)

This was rather a stego challenge. We were given a link to a website and it looks like a script has been made to produce an output of gif from several images.

![](<.gitbook/assets/Screenshot\_1 (7).png>)

After saving the image, I started performing the usual ctf tools: strings, stegsolve, binwalk and view hex. And then after using [zsteg](https://github.com/zed-0xff/zsteg), we manages to get output of the flag from one of the lsb.

![](<.gitbook/assets/Screenshot\_2 (5).png>)

The flag is **picoCTF{imag3\_m4n1pul4t10n\_sl4p5}.**

### tunn3l v1s1on

![](<.gitbook/assets/Screenshot\_5 (2).png>)

This was rather a quite hard and guessy challenge for me. In this challenge we were give a file. After looking at the header I was able to determine that it was a .bmp image.

![](<.gitbook/assets/Screenshot\_2 (4).png>)

I then proceed to try opening the image using image magick display since windows program was unable to open it directly.

![](<.gitbook/assets/Screenshot\_1 (6).png>)

From the displayed image, we can guess that this image hex value has been altered and not showing the whole picture.

![](<.gitbook/assets/image (6) (1).png>)

After some times of reading the bitmap information from this[ website](http://www.ece.ualberta.ca/\~elliott/ee552/studentAppNotes/2003\_w/misc/bmp\_file\_format/bmp\_file\_format.htm), I started to try and change the hex value of the image. After several days of break and taking a look back, I was able to produce the full image though the colors are not fully correct by changing these offset: 00Ah, 0012h and 0016h.

![](<.gitbook/assets/Screenshot\_3 (3).png>)

And the image we got is:

![](.gitbook/assets/adas.bmp)

The flag is: **picoCTF{qu1t3\_a\_v13w\_2020}.** This challenge taught me a lot about bitmap and how it was actually structured, I do think it deserve more points than most of the forensic challenges.

## General Skills

### Obedient Cat

![](<.gitbook/assets/image (69) (1).png>)

As the challenge name suggest, just use the cat syntax on the flag file.

![](<.gitbook/assets/image (70) (1).png>)

flag: **picoCTF{s4n1ty\_v3r1f13d\_28e8376d}**

### Python Wrangling

![](<.gitbook/assets/image (71) (1).png>)

Download the files, and use python to open them: `python3 ende.py -d flag.txt.en`

![](<.gitbook/assets/image (72).png>)

### Wave a flag

![](<.gitbook/assets/image (73).png>)

![](<.gitbook/assets/image (74) (1).png>)

It's an executable program, lets change the permision and run it.

![](<.gitbook/assets/image (75) (1).png>)

Flag: picoCTF{b1scu1ts\_4nd\_gr4vy\_18788aaa}

### Nice netcat...

![](<.gitbook/assets/image (76) (1).png>)

Use netcat on terminal.

![](<.gitbook/assets/image (77) (1).png>)

It gives numbers as output, let save it into txt.

![](<.gitbook/assets/image (78) (1).png>)

Based on the hint, it's from ascii, lets decode it to text with this [website](https://convert.town/ascii-to-text).

![](<.gitbook/assets/image (79).png>)

Flag: **picoCTF{g00d\_k1tty!\_n1c3\_k1tty!\_d3dfd6df}**

### Static ain't always noise

![](<.gitbook/assets/image (80) (1).png>)

The static is an exe program, change the permission and run it.

![](<.gitbook/assets/image (81) (1).png>)

Lets see the other file ltdis.sh

![](<.gitbook/assets/image (82) (1).png>)

It seems that this bash script is similar to `objdump` that is used to disassemble elf 64 files.

![](<.gitbook/assets/image (83).png>)

Using `objdump -s` option, gave us the flag.

![](<.gitbook/assets/image (85).png>)

**picoCTF{d15a5m\_t34s3r\_ccb2b43e}.**

### Tab, Tab, Attack

![](<.gitbook/assets/image (86) (1).png>)

Lets unzip it.

![](<.gitbook/assets/image (87) (1).png>)

Lets use `cat` syntax to open the unzipped file.

![](<.gitbook/assets/image (88) (1).png>)

flag: **picoCTF{l3v3l\_up!\_t4k18c}.**

### Magikarp Ground Mission

![](<.gitbook/assets/image (90).png>)

Lets connect to the ssh with the given credentials.

![](<.gitbook/assets/image (91) (1).png>)

This challenge just taught us to use the basic `ls` and `cd` command in the terminal.

{% file src=".gitbook/assets/Addadshashanammu.zip" %}

![](<.gitbook/assets/image (92) (1).png>)

flag: **picoCTF{xxsh\_0ut0f\\/\\/4t3r\_21cac893}**

## Binary Exploitation

### What's your input?

![](<.gitbook/assets/image (93) (1).png>)

Based on the hint lets see the python version of the file.

![](<.gitbook/assets/image (94) (1).png>)

It was created with python2 which has vulnerability in the input() function. This is the main reason why people have converted to python3. We can exploit it using `import('os').system("put command here")` in the input.

![](<.gitbook/assets/image (95) (1).png>)

flag: **picoCTF{v4lua4bl3\_1npu7\_8433797}**

### Binary Gauntlet 0

![](<.gitbook/assets/image (96) (1).png>)

### Stonks

![](<.gitbook/assets/image (115).png>)

## Conclusion

Overall I really enjoyed the ctf. As a solo player, I was able to learn a lot of things especially in reverse engineering and bin exp. Hopefully I will be able to solve more challenge in the upcoming CTFs.
