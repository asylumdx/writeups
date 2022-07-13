# 🦌 Hack@10 2021 Writeup

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FuKd4NnPR0bfIvdi4rSGn%2Fss.jpg?alt=media\&token=4b958630-7e9f-48a7-bcff-4c83e6c3b5f1)

Final scoreboard of the CTF

### &#x20;<a href="#_g35zcx9z0f7" id="_g35zcx9z0f7"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FrbmsJEyROXInLHjswYBS%2F1?alt=media)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FDuzt52hz3fPGOEqzfo5J%2F2?alt=media)

924<\`\_LbKA+0=b>\_?0dBFbbKJN .

Input the string on [Cyberchef](https://gchq.github.io/CyberChef/) to decode it using ROT47

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FuPSyqhkNXn1GP1dSqZs7%2F3?alt=media)

And yeah we got the flag! Ez! **hack10{3zpZ\_l3m0n\_5qu33zy}**

### &#x20;<a href="#_msivg7ovusua" id="_msivg7ovusua"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FOBsN34AZYryjJ6c4mktd%2F4?alt=media)

At first we try to find hidden sheet, which is Sheet 2 and 3 but

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fu0xzajbxFdsSSk1y11TX%2F5?alt=media)

That is not the flag :( so we proceed with trying to extract the data from the xlsx file since we know that xlsx is just a [zip compressed file](https://www.lifewire.com/what-is-an-xlsx-file-2622540). We can do this with the binwalk command \_binwalk --\_dd='.\*' file.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2F5BSI7fVOF5fsmhgfLhlK%2F6?alt=media)

Then proceed to unzip the remaining files.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2F8LdKcDQjyMLmHjlSD1DK%2F7?alt=media)

After that, we can try to grep the strings on the directory with the flag format by using command grep -R 'string' dir/ . Although we can only grep the fake flag, we also see a base64 text in the one of the file from the directory.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FMxgPkGNKtztkwnxU8FsW%2F8?alt=media)

Decode the string from base 64 and we get the flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FlYJeLfdepWQIx1IcxUs4%2F9?alt=media)

**hack10{4h\_lov3ly\_ch33s3c4k3}**

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FbmhA4pw06nFBqz1vJe9Z%2F10?alt=media)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fiis7n7xqmruPXNbi4dVZ%2F11?alt=media)

**😤🤟** First blood! Sheeesh!

I am not sure if this is the intended solution but after downloading the[ powerflag.pttm](https://drive.google.com/file/d/1PTfiDF5iGtuDXbJ7\_wJHRTJv6BiEqzTb/edit) file. We treated this challenge the same as the cheesecake challenge. Proceed to extract data from the file with \_binwalk --\_dd='.\*' file

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FdDEu6zUQn3Nf7idDi2Vb%2F12?alt=media)

After unzipping the remaining file, we can see lots of images in one of the folders.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FnUAwen2qJervokzrOqYl%2F13?alt=media)

From image60.png, we got our flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FgHtGrRplMWtoeTpZygJI%2F14?alt=media)

**hack10{p0w3rup\_ur\_p0w3rp01n7}**

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fll1VS8aOoDAMHVoRtYPB%2F15?alt=media)

Hint: “143 _**word**_ to open my heart” and “The art of hiding is part of love”

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FKkrekw3yfp0JbzL5Gnn3%2F16?alt=media)

After scanning the QR code, we got ''I Love You'' so that is our secret key, then we use **steghide** because of the hint “The art of hiding is part of love” and yes, we love steganography!

Let’s help him solve his brokenheart issue!\\

$ steghide extract -sf brokenheart.jpg

Enter Passphrase: ILoveYou

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FZWmdim17gM6nX1xdkztc%2F17?alt=media)

But the QR code is unlikely to be readable, so we re-draw it using [qrazybox](https://merricx.github.io/qrazybox/)​

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2F2dBtCdy8i9tqVX3AKtQE%2F18?alt=media)

and finally we got a readable QR code! And let’s extract the data from the QR code!!!

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FddAc8kqYWczaDwZ3bRiZ%2F19?alt=media)

**hack10{br0k3n\_QR\_c4n\_b3\_f1x3d\_n0t\_br0k3nH34rT}**

Legends believe that the author still heart broken 💔

### &#x20;<a href="#_cpg9e1lwbnzs" id="_cpg9e1lwbnzs"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2FOPQl7RsVzIE2nRcA7fv7%2F20?alt=media)

Let’s try binwalk for this picture $ binwalk --dd='.\*' matabatin.jpg

And sheeeeesh! A flag :) **hack10{4s\_aBov3\_5o\_Bel0w}**

For this challenge, we get an mp3 file with scratchy noise. Just use Sonic Visualiser > add Spectrogram > set Window 256

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-212f1d79d9243bc49f591fb62fa45b3017f6ad70%2FPicture1.png?alt=media)

**hack10{1m\_t1R3d\_0f\_Mc0\_jkjk}** Easyyyyyy Peasy!\\

### &#x20;<a href="#_saepiv1qnvmo" id="_saepiv1qnvmo"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-e2efd48329c88a5c3ff447b221efa6e44d40f19a%2FPicture2.png?alt=media)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-27377d334973d83dd2f85397be336ae600037e49%2FPicture3.png?alt=media)

Let’s just decode it. It’s a Tic-Tac-Toe! We then proceed to decode the symbols [here](https://www.dcode.fr/tic-tac-toe-cipher)​

**hack10{TICKITYTACKITYTOE}**

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-bce81bb00eb5c73119b1220b1422c85b08a9e52c%2FPicture4.png?alt=media)

From this question, we got PiedPiper jpg file

Since we didn't know what type of cipher it is, we proceed to reverse search the image using [Yandex](https://yandex.com/images/). From one of the results, we manage to find out that it is a Pig Pen cipher.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-bac4f5253941690cce96fcd04b9c6689ee582ab3%2FPicture6.png?alt=media)

Then, we decode the cipher using [dcode.fr](https://www.dcode.fr/pigpen-cipher) and manage to get ‘avadakedavra’ as an output.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-76f6f28c06de91ec274d8db726a84d5c9235f7a2%2FPicture7.png?alt=media)

As it is not a flag, we tried to extract more data from the original image using binwalk.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-4f55c185ac1ee62c4872f48d331cb72e039de772%2FPicture8.png?alt=media)

From the extracted data, we got a zip file that requires a password. Proceed to enter ‘avadakedavra’ from the decoded cipher as the password.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-82450764ca0beaaadcc012846ff416588179e77a%2FPicture9.png?alt=media)

And we managed to get the flag file.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-1fe1fa8ce6fdd55ebed3a70142deaa577782454d%2FPicture36.png?alt=media)

### &#x20;<a href="#_35m1fqo4dhxa" id="_35m1fqo4dhxa"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-855d4386950a0b36bdf7afc30f662ff1a2703b4f%2FPicture10.png?alt=media)

We got a pcapng file and opened it in wireshark. Filtering with http, we could see that the user was accessing a website at [http://192.168.175.123:9001](http://192.168.175.123:9001/).

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-b73148fac6f0f1d0e33510f27f669b5cfcf299c8%2FPicture11.png?alt=media)

Right click on one of the packets and click on follow tcp stream, we can see the host and source code of the website the user accessed.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-9ae14cf863fc31f6d7d39cd08cbb28a38795a3a0%2FPicture12.png?alt=media)

Proceed to save the source code into a file such as neighbour.html and open it one a browser. It seems that the page is not working.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-213706bc91a45d96e50f769d6dba9781cb063e48%2FPicture13.png?alt=media)

Based on the console error, we need to change the location.origin into an ip address and port such as http://192.168.175.128:9001 .

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-827bc37e00b2e05513dcaafa7eca52eff47e9841%2FPicture14.png?alt=media)

Open the html file again and we can see a website with a drawing function using the mouse.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-1f3ae2a3c96f8bdfffe30b5faebdfa8e486353bb%2FPicture15.png?alt=media)

Based on the source code, we know that the website was made of html canvas, websocket and nodejs. After learning how to create the page from[ this website ](https://wesbos.com/html5-canvas-websockets-nodejs), we know that the websocket was used to send the coordinate of the user's mouse to the server. By using the ‘websocket’ filter on wireshark, we were able to see the mouse coordinate sent to the websocket server.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-706927077af66cb5d59a3f68f23c15597ae84afa%2FPicture16.png?alt=media)

From this [writeup](https://www.cyborgsecurity.com/cyborg\_labs/cyborg-security-2020-ctf-solutions/), we learn to dump the websocket data by using [tshark](https://www.wireshark.org/docs/man-pages/tshark.html).

$ tshark -r neighbour.pcapng -Y websocket.payload -E occurrence=l -T fields -e text

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-326a841e203002c921a8b160c8370f1d349b5183%2FPicture17.png?alt=media)

Then, we used [this website](https://www.mobilefish.com/services/record\_mouse\_coordinates/record\_mouse\_coordinates.php) to map out the mouse coordinates.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-86ff370fa3bef1d446d694c2681845e1f9a6496a%2FPicture18.png?alt=media)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-81d2f9b9a4e6f5e94863742d7b3e529380cd58e6%2FPicture19.png?alt=media)

**hack10{why\_chu\_spy\_0n\_m3???}**

Credits to write ups and site for idea:

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-10068147d376394b572a1958cd21406b3a61e49d%2FPicture20.png?alt=media)

After downloading the Odyssey.ova file, we tried to open it using vmware but failed. Then, we proceed to use Virtual Box Oracle. However, it seems to be stuck at the booting process with multiple errors.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-6860d7d1155ad3eba35986255ad608603f19336c%2FPicture21.png?alt=media)

After trying to change the settings of the image file for a couple of hours, we noticed that it uses Genymotion Startup while trying to boot.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-2d68bd94657cdec0034f7722b03e21efb31db04f%2FPicture22.png?alt=media)

After some googling, we found out that we can use Genymotion alongside Virtual Box to boot android devices. We downloaded [Genymotion](https://www.genymotion.com/download/) and registered for the free account. Opening the app, it recognized our already installed Google Pixel XL device from Virtual Box and we just start it to successfully boot it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-2b69bfe48877133edcd8994dcb7a1601ecd78014%2FPicture23.png?alt=media)

After booting, we get a home screen same as most Android devices. We proceed to check the common places such as gallery, audio, and email.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-0314a8a4ec9d4888722b551970fca5797c64a1b0%2FPicture24.png?alt=media)

Then proceed to open Amaze application also known as a file manager and saw a file named flag1 in the device directory.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-9560050a777e4c80ed33fc4359794790bcabff33%2FPicture25.png?alt=media)

Inside the file we got the flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-6dd114d3b5b560f8e2abe3cce2b264f400372874%2FPicture26.png?alt=media)

**hack10{Gl4d\_t0\_S33\_yOu\_hEr3}**

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-a1ca128e26ab61f697933333d004e718f8738526%2FPicture27.png?alt=media)

In this challenge, we open the ES Explorer and use the storage analyze feature to check for any weird or recently created file.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-657839db1014b7d8a29e7772e120d2101543c98e%2FPicture28.png?alt=media)

From one of the recently created files, we got several redundant flag files.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-62e8e693ec7625c0159705c90ab460396a6f67ba%2FPicture29.png?alt=media)

We noticed the flag069.bin file(nice) and opened it. Inside we get the second flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-e4bd4a588436961bdd30f1b793b638f89f5be594%2FPicture30.png?alt=media)

**hack10{W3lc0me\_T0\_m03b1lE\_f0ren5iC}**

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-ab86ea13d3167226e46c4d0f2755e229be416dd7%2FPicture31.png?alt=media)

Opening the Messaging app of the device, we get to see several conversations that seem to lead to the third flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-600942825d3548263408c53cd225f03ed04d3f18%2FPicture32.png?alt=media)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-e20aebd0ef29e8faeb0ff41a1401bf02a4b2957a%2FPicture33.png?alt=media)

Opening the link leads us to a dropbox file that stores a file artifact.docx . It seems blank, we downloaded the file to explore the content of the docx.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-99b945f51c7dce9ba147a834e05f7137b48f3801%2FPicture34.png?alt=media)

We highlighted the whole docx using Ctrl + A and chose the red colour. It seems like someone tried to hide these texts. Although it looks gibberish, we managed to extract a readable flag at the end of some paragraphs and combine it to form a flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MWEN\_\_ASIV1YRyhrCvN%2Fuploads%2Fgit-blob-207addb28d0092667a13b6c9e4f5f251d0cd20d5%2FPicture35.png?alt=media)

**hack10{tH3\_unKn0WN\_Of\_ThE\_L0nG\_lO5T\_4RT1f4ct5}**
