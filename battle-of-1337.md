# 📍 Battle Of 1337

![](.gitbook/assets/0)



### BATTLE OF 1337 <a href="#_toc109087281" id="_toc109087281"></a>

![](.gitbook/assets/1)

### Reverse Engineering <a href="#_toc109087282" id="_toc109087282"></a>

### Simplify <a href="#_toc109087283" id="_toc109087283"></a>

![](.gitbook/assets/2)

First, I checked the filetype and it turn out to be elf64 binary. Tried running and it ask for code.

![](.gitbook/assets/3)

![](.gitbook/assets/4)

Then I open it in IDA to see the main function.

![Graphical user interface, application

Description automatically generated](.gitbook/assets/5)

Decompile the function using hex ray by pressing f5.

![](.gitbook/assets/6)

From here we can see how four variable that is being used for checking the code.

3 \* v7 + v4 == 18044 && 3 \* v6 \* v5 == 5174190 && v4 == 1010 && v7 + 49363 \* v6 == 63683948

Since we have v4 value, we can just calculate other value using math.

V4=1010

V5=1337

V6=1290

V7=5678

![](.gitbook/assets/7)

BO1337{1010-1337-1290-5678}

### WEB <a href="#_toc109087284" id="_toc109087284"></a>

### Break The Storage <a href="#_toc109087285" id="_toc109087285"></a>

![](.gitbook/assets/8)

First, login using the given credentials.

Username: **BattleOf1337**

Password: **BattleOf1337**

![](.gitbook/assets/9)

Then, I checked the response request for one of the file loaded in the page and among them is profile.js, inside the file, we can see the flag.

BO1337{a2c13e70ff50376e259ddb5bd5e54a69b16e569f}

### Cat-Dalmantion <a href="#_toc109087286" id="_toc109087286"></a>

![](.gitbook/assets/10)

https://ifelse.battleof1337.com/

![](.gitbook/assets/11)

Opening the site, I didn’t notice anything at first. Pressing the buttons only changes the background of the site. I proceed to see the request in burp to inspect it further.

![
Description automatically generated](.gitbook/assets/12)

We can see a Flag parameter in the response.

BO1337{kuc1n6\_5374n}

### NET <a href="#_toc109087287" id="_toc109087287"></a>

### Semerah Padi <a href="#_toc109087288" id="_toc109087288"></a>

![](.gitbook/assets/13)

We are given a pcap file “flaghere.pcap”, proceed to open in Wireshark.

![](.gitbook/assets/14)

Follow the HTTP/TCP stream of the packets to see the file downloaded by the user.

![](.gitbook/assets/15)

We can see the file contains a lot of dummy text in latin, however among the text we can see one line of text that isn’t latin with “/” which usually comes from url.

![](.gitbook/assets/16)

Trying some Caesar decoding tool, I finally get an output using CyberChef Caesar Box Cipher at the 15 height. The decoded text is a pastebin url: https://pastebin.com/5WNzAUve.

![](.gitbook/assets/17)

Inside the pastebin is two ufile.io file which kept two audio file.

![](.gitbook/assets/18)

![](.gitbook/assets/19)

Using sonic visualizer, we can see the spectrogram of the audio. The .wav file spectrogram contains the flag.

BO1337{2878f7b0f8deea26a66d642ebe045620efc43091}

### Streamline <a href="#_toc109087289" id="_toc109087289"></a>

![](.gitbook/assets/20)

Downloading the image, we can see a picture containing a lambo and an orange cat

Proceed to use some steganography tools including steghide.

Managed to extract a .cap file from the image.

Opening the file in Wireshark, we can see it contains packet from a wifi network. From the challenge description, we have to crack the wifi password from the packets using the hint give. We can use aircrack-ng to crack the wpa handshake, however we need to have a wordlist. The description given of the wifi password is:

\- pet name

\- one symbol

\- 4 digit car plate number

From this description, we can conclude and guess the password. Since the pet is an orange cat, we Malaysian often call them oyen. I proceed to generate a wordlist using crunch with the details:

\-8 characters

\-start with oyen

\-^= all symbols

\-%=number from 0-9

Crunch will generate the wordlist for us.

Using the wordlist, we can start cracking the password, and finally get the password which is oyen@9367.

BO1337{oyen@9367}

### OSINT <a href="#_toc109087290" id="_toc109087290"></a>

### Back To The Future <a href="#_toc109087291" id="_toc109087291"></a>

From challenge name we can guess that we have to see the website from previous date. Using wayback machine we can see the the site has been indexed on 4 July. Opening the site present is with flag.

[https://archive.org/web/](https://archive.org/web/)

BO1337{aHR0cHM6Ly9veW0uY2F0bWUuY2Y=}

### 1Gram <a href="#_toc109087292" id="_toc109087292"></a>

We can search for any Instagram @ from the website and found one @mikrahazura.

Going to instagram profile, we can see part of the flag.

One of the image tagged several profile.

One of the profile contains the next part of the flag.

Proceed to repeat the process, and combine the flag.

BO1337{S74LK\_4P4\_7U?}.

### Snap <a href="#_toc109087293" id="_toc109087293"></a>

From the previous challenge, we can see another profile

Caption says “dimanakah saya”. I noticed that the profile image on this profile wasn’t completed.

I proceed to download all the profile pictures and used canva to combine the image.

From the grid on the picture, we can guess that we need to use profile picture of other profiles to get the full image.

After getting the full image, I started using reverse image search on Google to find any similar image.

From here we know that the image came from Imbi MRT. I was confused on where the flag was and opened a ticket on whether we need to fill the BO1337{flag} format ourself in order to submit and the admin answered yes. It’s pretty confusing to be honest since no declaration in description.

BO1337{Imbi}

### MISC <a href="#_toc109087294" id="_toc109087294"></a>

### Rayquaza <a href="#_toc109087295" id="_toc109087295"></a>

First we can check the file type, it turns out to be a GBA rom. To run the rom, we can use any GBA emulator such as VBA, but first we must rename the file to 1337Pikachu.gba.

Opening the game, it turns to be a pokemon emerald rom.

After talking with the mom and stuff we proceed to go out and find the fat man from the description and he gave us the flag.

BO1337{91091b84a367c97a93eb7b5ba35e850e}

### Heihawru <a href="#_toc109087296" id="_toc109087296"></a>

Opening the .txt file, we can see encoded text and numbers with ?:?:? format, I proceed to decode it using [dcode.fr](https://www.dcode.fr/caesar-cipher) Caesar cipher tool.

Turns out to be a song lyric. From here, I start to guess the relation between the lyrics and the number and realize how to decode it. Taking 5:6:2 as an example:

5=Number of lines.

6=Number of words.

2= Number of characters.

Proceed to do the same using other number and we will get flAgisdarK3noKluai.

BO1337{darK3noKluai}

### GunTher

Treating the challenge as steganography, I proceed to use all the audio stega tools such as spectrogram,steghide,binwalk etc.

Finally using Deepsound, I manage to extract an image containing the flag.

BO1337{9d6382bf597a3014a8472762fedce888}

### Sheng Xiao <a href="#_toc109087297" id="_toc109087297"></a>

Downloading the image, we can see encoded text, from description we can guess it uses the same cipher from zodiac killer.

Searching for some online tools, finally found one that was able to decode the text.

[http://zodiackillerciphers.com/typewriter/](http://zodiackillerciphers.com/typewriter/)

BO1337{f4ec90216d2d7d5edb7c201919fce008e8}

### Darchrow <a href="#_toc109087298" id="_toc109087298"></a>

The image contains text.

To extract the text, we can use OCR tools such as : [https://www.imagetotext.info/](https://www.imagetotext.info/) however we still need to correct the extracted type. From the challenge name darchrow, we can google and know that it is the hero used in Dota which is now known as enigma in Dota 2.

ACZQQOKLHUALHPTXGXKEPWTLDJUCEORHRKTQRTVKXOWRBYACB UKRUPCEAQRAKMZRJHCEHZJWJKSGTLTMOXTEJHLPPEHXJBQQW KXYQNKFTOKBJUVFRUFCSQMTXHTTDJSOFWHYNSOHVEZGQVURJF JALJEXQWWYWIZBJLMOYDMGNXOMRMLQRSYWZHJGBLCSHNMYFXE SJNFBBITRXHKZYQGYIPEUYTNFXSSPCXIZJMRCTLHUUHBFEXIVBM EURYMPAZATXUVNVQRSLPFVWWBBUHOEMXYRPMLTYZXLHSAPMMM QOEHXKQCDWBSWDMTFMSMFBNCQGMQHHJPQYKJPZNMYYDKZYZX UHOOHAIAFGMDBMYAEQPRSUVQKGEZSA

I knew about the enigma cipher that was used during the word war and proceed to use the tools from dcode.fr to decode it.

https://www.dcode.fr/cipher-identifier

ISTOPENQUIRESTOPFORYOUSTOPTOREADANDDECRPYTTHISSTOPFORALANTURINGSTOPFORHISSUCCESSSTOPOFDECRYPTINGSTOPALLTHEGERMANSTOPMESSAGESTOPTHEFLAGISBOBRACESENIGMAFORALANTURINGBRACESONLYTHOSEWHOAREASLEEPDONTMAKEMISTAKESGETNOCRITIQUESEEMSEVERYBODYSWORRIEDBOUTTHINGSTHATWEARETHINKINGANDWHENTHEREMEDYSTHEENEMYYOUHIDESELFDEPRECATIONUPYOURSLEEVEANDSELFSERVINGFRIENDSWHOLEAVEWHENYOUARESINKING

BO1337{ENIGMAFORALANTURING}

### RedPoint <a href="#_toc109087299" id="_toc109087299"></a>

Probably one of the most ridiculous challenges. I spend hours trying to extract flag from the image and the file name. When I saw some people started getting the answer, I realize I was overthinking it. Basically, the flag is just what the arrow is pointing at which is the screwdriver.

BO1337{screwdriver}
