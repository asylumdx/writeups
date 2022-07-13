# 🐃 Pico CTF 2021 Writeups

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0dot1KBvh5AV4pwVC%2F-MX0lo\_h8USRBW9-j-Il%2Fimage.png?alt=media\&token=6e8f4370-87db-40c6-a0b7-a6eabe3fe078)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0dot1KBvh5AV4pwVC%2F-MX0lzdL0Xd60b39LlQL%2Fimage.png?alt=media\&token=e8e45793-c42a-4fb1-87ad-905747d5f9e6)

### &#x20;<a href="#web-exploitation" id="web-exploitation"></a>

### &#x20;<a href="#ancient-history" id="ancient-history"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWoaGcNQ420GhTSSaEO%2F-MWohAegow1V23WLntcS%2FScreenshot\_3.png?alt=media\&token=15ca01d5-d451-4721-a91b-a4c223259174)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWoaGcNQ420GhTSSaEO%2F-MWohErs37X4Gvqgs3Yp%2FScreenshot\_1.png?alt=media\&token=a15ddcee-d6ba-4223-96a1-99ad5880b4c0)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWoaGcNQ420GhTSSaEO%2F-MWohIY\_wHbcbpsbH94s%2FScreenshot\_2.png?alt=media\&token=5483eb8d-fffc-469f-87ea-0a9ea43e8f20)

Found the flag amongst the obfuscated code. **picoCTF{th4ts\_k1nd4\_n34t\_3bed1170}**

### &#x20;<a href="#get-ahead" id="get-ahead"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWoaGcNQ420GhTSSaEO%2F-MWoixSqRkf5qPjmqTa\_%2Fah1.png?alt=media\&token=b0836cfc-f333-4462-9f02-3c51902231cd)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWoaGcNQ420GhTSSaEO%2F-MWoj0n\_LVj5q77W\_CP6%2Fah2.png?alt=media\&token=2a28bc4a-25af-4a2f-8c9b-c5318d5f12e8)

Based on the challenge title, we should try get the website header either using curl or Burpsuite. curl command : `curl -X HEAD -i` [`http://mercury.picoctf.net:47967/`](http://mercury.picoctf.net:47967/)\`\`

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWoaGcNQ420GhTSSaEO%2F-MWojF6R1WIzZl15KG1Z%2Fimage.png?alt=media\&token=b4c75612-87e5-4917-becb-104ce25943fe)

and we got the flag from the header. **picoCTF{r3j3ct\_th3\_du4l1ty\_cca66bd3}**

### &#x20;<a href="#cookies" id="cookies"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWoaGcNQ420GhTSSaEO%2F-MWojYxIu\_\_pkwKe7ek5%2Fimage.png?alt=media\&token=18bd3c8a-b13d-476a-812d-7a536e9637d2)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWoaGcNQ420GhTSSaEO%2F-MWojc2HkTooR8pehbzo%2Fimage.png?alt=media\&token=26e55b5b-11a4-4c1c-ad53-c67cbe7ad781)

The title and hint of the website talks about cookies, lets view the cookies using the in browser function.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWoaGcNQ420GhTSSaEO%2F-MWojq4nG-jNoWYXATkm%2Fimage.png?alt=media\&token=68b4d4c7-ce03-405e-80e7-53f8d1904eff)

The current cookie value is -1, lets try changing it to 1and see if we get any output.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWoaGcNQ420GhTSSaEO%2F-MWok8gr9PeQDDQY7hsN%2Fimage.png?alt=media\&token=a9baac17-ef51-4038-b6a4-6c798e5b6b30)

Based on the output, we need to traverse and try different value of cookies to get the flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWoaGcNQ420GhTSSaEO%2F-MWokaW-fbJhgeumFJXH%2Fimage.png?alt=media\&token=eee85386-b3f6-499a-84ca-3ba63e91b9f5)

And we got the flag on the 18 cookies. **picoCTF{3v3ry1\_l0v3s\_c00k135\_064663be}**

### &#x20;<a href="#scavenger-hunt" id="scavenger-hunt"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWonr4J4GJR5BOc7CSo%2Fimage.png?alt=media\&token=4ec3a6d2-08af-4399-b605-45c15a8e0113)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWonxsV7tJmeBzqfts7%2Fimage.png?alt=media\&token=d646dfcf-420c-4d06-9034-020eabe4b136)

Seems like a normal html website, lets take a look at the source.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWoo3RUpvFYS-SL30rO%2Fimage.png?alt=media\&token=bc4c4ada-2305-4109-871a-c64b7b4a13f9)

It seems that this is a directory traversing challenge, we got the first part picoCTF{t from the source. It says the website was made from html,css and js. Lets take a look at those.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWoqqoxk5iNs4GVe4YI%2Fimage.png?alt=media\&token=99c279a7-c57c-4e64-906b-9bfeb9d0ccd5)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWooPSZkEYJJ0nhzawR%2Fimage.png?alt=media\&token=8a048244-d08b-4f8e-8667-d4ff08d8c1e4)

We found a js script, lets open it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWoo\_4QMLlqm7TOk933%2Fimage.png?alt=media\&token=e7c9280a-0933-492f-8b56-a0d3191ca925)

From the hint, we can guess the next part is in robots.txt that is used to configure crawler from accessing certain directory of the website.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWor1pu71XKKClYMLME%2Fimage.png?alt=media\&token=26cd5fec-368f-40a5-8633-36c8ed59b19b)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWorD7LYFQYTs1nePdX%2Fimage.png?alt=media\&token=214ab69a-bbff-4996-8b2d-9f4a3dbcacd1)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWorMZ9j1AaE\_Al11Z7%2Fimage.png?alt=media\&token=ab7a105f-ee8c-4be5-a1b8-a22641bc2024)

5th part: \_f7ce8828} . flag: **picoCTF{th4ts\_4\_10t\_0f\_pl4c3s\_2\_100k\_f7ce8828}**

### &#x20;<a href="#who-are-you" id="who-are-you"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWorr0RLpWS0-ZMDP32%2Fimage.png?alt=media\&token=340ef060-f42e-4eec-95b2-bcf2728ce398)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWos8Rh7mPk3RE0nT09%2Fimage.png?alt=media\&token=cd757c58-5137-423a-9f66-7ffe28aff602)

Opening the website told us that we can only access it with picobrowser. From reading past writeup, it seems that we need to change the user agent to access it. We use the curl command : `curl -A "PicoBrowser" http://mercury.picoctf.net:46199` to change the user agent.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWoswcvWnFzaS2e5\_Dc%2Fimage.png?alt=media\&token=8da97857-13e9-4b9f-b024-fe9ba7922a90)

From the website, it asks us to visit the website, from the website itself. We can use curl command : `curl -A "PicoBrowser" http://mercury.picoctf.net:46199/ -H "Referer: http://mercury.picoctf.net:46199"`

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWpB-pwLDDFfztKxc1x%2Fimage.png?alt=media\&token=e9970768-9527-44f2-8d5d-27cda8f4d46b)

Next it asks us to access the website from 2018. We can modify the time header through: `curl -A "PicoBrowser" http://mercury.picoctf.net:46199/ -H "Referer: http://mercury.picoctf.net:46199" -H "Date: Wed 17 Mar 2018 02:47:59 GMT"`

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWpCk7pMJ2noUqVmKGZ%2Fimage.png?alt=media\&token=dfdc7bd5-9565-4796-9e88-43a4ff1e4177)

Now it asks us to send request without being tracked. We can use the DNT(Do Not Track) header curl command: `curl -A "PicoBrowser" http://mercury.picoctf.net:46199/ -H "Referer: http://mercury.picoctf.net:46199" -H "Date: Wed 17 Mar 2018 02:47:59 GMT" -H "DNT: 1"`

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWpD8gDqEff-69H1kcP%2Fimage.png?alt=media\&token=7847cec0-1baa-4e2b-beab-b1ee58a219af)

Now it only allows people from Sweden. We just need to use a sweden ip and X-Forwarded-For header to foward our curl request ip. `curl -A "PicoBrowser" http://mercury.picoctf.net:46199/ -H "Referer: http://mercury.picoctf.net:46199" -H "Date: Wed 17 Mar 2018 02:47:59 GMT" -H "DNT: 1" -H "X-Forwarded-For:193.150.233.115"`

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWpMv4l7YW5Y2ldB\_6L%2Fimage.png?alt=media\&token=e105ee18-678f-444e-a934-82872427369f)

Now it also want us to speak in Sweden. We just need to change the language header using the syntax: `curl -A "PicoBrowser" http://mercury.picoctf.net:46199/ -H "Referer: http://mercury.picoctf.net:46199" -H "Date: Wed 17 Mar 2018 02:47:59 GMT" -H "DNT: 1" -H "X-Forwarded-For:193.150.233.115" -H 'Accept-LAnguage: sv'`

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWonHr7Hq7XBZ\_ZT3cT%2F-MWpNVcixR6Z-aJQvIvO%2Fimage.png?alt=media\&token=e329558b-2b5d-4b38-831d-65cea9b91f3e)

And we finally got the flag. **picoCTF{http\_h34d3rs\_v3ry\_c0Ol\_much\_w0w\_8d5d8d77}**

### &#x20;<a href="#some-assembly-required-1" id="some-assembly-required-1"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWpNak2NoJhiU-Sa\_Rm%2F-MWpNv-iIuRtT1zOcvod%2Fimage.png?alt=media\&token=c623b737-3cd5-4faf-bff3-41e161eee81f)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWpNak2NoJhiU-Sa\_Rm%2F-MWpO46RCJkTAABpPKBP%2Fimage.png?alt=media\&token=bd349d74-c10b-4854-9d85-59085ac031ea)

This challenge is straight forward. We just need to look for the wasm files in the debugger browser function to get the flag. **picoCTF{8857462f9e30faae4d037e5e25fee1ce}**

### &#x20;<a href="#it-is-my-birthday" id="it-is-my-birthday"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWpNak2NoJhiU-Sa\_Rm%2F-MWpOqLfajOeyFKQ2qbf%2Fimage.png?alt=media\&token=16dc77d1-67d9-45cc-a86f-73df7853454d)

This challenge is about the md5 hash collision that makes it unsecure.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWpNak2NoJhiU-Sa\_Rm%2F-MWpP24F\_3xsK3hLNikH%2Fimage.png?alt=media\&token=dd59fc7a-ec21-449a-83b8-9a025e58d94f)

The website requires us to upload two different pdf files with the same hashes. It also has an upload limit not allowing for more than 100kbs files. By using this [website](https://www.mscs.dal.ca/\~selinger/md5collision/), we got two exe program with md5 hash collision.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWpNak2NoJhiU-Sa\_Rm%2F-MWpQyMSCCz9aIaEWTR4%2Fimage.png?alt=media\&token=b27e2b86-db22-42e2-855b-df3e979068a9)

Now since the php script only requires the uploaded files to have .pdf extension, we can just rename the files and add .pdf before uploading it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWpNak2NoJhiU-Sa\_Rm%2F-MWpRKbHtNaiUsEvQaO2%2Fimage.png?alt=media\&token=afe4e823-4110-4811-9699-115e8b65e564)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWpNak2NoJhiU-Sa\_Rm%2F-MWpRSmVnpPu-ERFPkr3%2Fimage.png?alt=media\&token=7202e577-18be-4f2c-bb9f-509287fece6b)

And we got the flag. **picoCTF{c0ngr4ts\_u\_r\_1nv1t3d\_73b0c8ad}**

### &#x20;<a href="#most-cookies" id="most-cookies"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtMa1RNwKPBpKLpArH%2F-MWtOHdza4Q8Br3rgcrK%2Fimage.png?alt=media\&token=34925354-159a-43b2-90a7-8da4a2a03333)

This challenge is about cookie forging. We were given a website and the server source code.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtMa1RNwKPBpKLpArH%2F-MWtOZtQBnqImt8QBmBO%2Fimage.png?alt=media\&token=8f915b45-64fd-4012-9fd1-f390ca02c461)

From the challenge description, we know that the website uses flask cookies. Flask cookie was made by using a 'secret key' to ensure it's secure. Let's see the value of the cookie using [flask-unsign](https://github.com/Paradoxis/Flask-Unsign).

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtMa1RNwKPBpKLpArH%2F-MWtR-l7oq0q9y2Gxc17%2Fimage.png?alt=media\&token=2d016149-2772-4134-8d8b-fbb528dea821)

Here we can see that the value is blank. However from the source code server.py, we can see that in order to get the flag, we need to set it to admin.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtMa1RNwKPBpKLpArH%2F-MWtRMplue9WZF7R2z7\_%2Fimage.png?alt=media\&token=9da65582-9d13-4b3f-82f1-1cac05a09e8e)

Before continue to forge it, we need to find the secret key of the flask cookie.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtMa1RNwKPBpKLpArH%2F-MWtRiR7nlhTsVHoNlz8%2Fimage.png?alt=media\&token=3d0c5eaf-bf1c-454e-9ed3-b60bdf246a62)

Here we can see that the secret key is chosen randomly from a list. We can bruteforce the wordlist by using [`flask-unsign`](https://github.com/Paradoxis/Flask-Unsign) feature.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtMa1RNwKPBpKLpArH%2F-MWtSp\_H7QHzf9nEILM4%2Fimage.png?alt=media\&token=30cc81ae-2265-462d-a3e7-8560f0f163c0)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtMa1RNwKPBpKLpArH%2F-MWtTOQa\_k4a7B-h2zag%2Fimage.png?alt=media\&token=e5665540-0293-41b9-b7b5-5e19e5d352bd)

From the bruteforce, we found out the secret key is butter. Now we can forge a new cookie with value:admin and secret key: butter.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtMa1RNwKPBpKLpArH%2F-MWtUK10L1YBKUgpZTrt%2Fimage.png?alt=media\&token=f2143a00-0fff-47f1-b8a6-ca76714e45e0)

Now change the cookie value on the browser to get the flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtMa1RNwKPBpKLpArH%2F-MWtUVqcyrl6PAC\_XNnV%2Fimage.png?alt=media\&token=2eee679b-e51f-447d-b4e8-49916b7e55f5)

flag: **picoCTF{pwn\_4ll\_th3\_cook1E5\_743c20eb}**

### &#x20;<a href="#cryptography" id="cryptography"></a>

### &#x20;<a href="#pixelated" id="pixelated"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_CauPy1rXt5uTfbcC%2F-MW\_EQT2wePe6pW463nh%2FPixelated.png?alt=media\&token=b072fd01-6bcf-4a19-8045-d5a4aca962f1)

For this challenge we were given two images that seems to be made out of statics.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_CauPy1rXt5uTfbcC%2F-MW\_FCbtEI1eBVx9yJW7%2Fscrambled1.png?alt=media\&token=55428df7-363c-492b-9e15-39ec5a701253)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_CauPy1rXt5uTfbcC%2F-MW\_FIKANfGG4TtVrH-6%2Fscrambled2.png?alt=media\&token=a3e8d775-9aa2-4a7a-857e-4627efd67065)

I treated this challenge as steganography and used [StegSolve](https://github.com/eugenekolo/sec-tools/tree/master/stego/stegsolve) to combine both images to produce an output.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_gQCbHORcncCdlEQl%2F-MW\_i5yimcEs9-JT3xyV%2FScreenshot\_1.png?alt=media\&token=7a690f6f-05e5-4d96-a613-750c19093be0)

After combining both and using the ADD function we can see the flag **picoCTF{0542dc1d).**

### &#x20;<a href="#mod-26" id="mod-26"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtUZtsNGIfv\_gtH10g%2F-MWtUkP6aH7lTbCNMq5a%2Fimage.png?alt=media\&token=5f162d00-0cc5-468e-8ac3-024522d80cbc)

It's a simple rot13 encryption. Let's use [CyberChef](https://gchq.github.io/CyberChef/#recipe=ROT13\(true,true,false,13\)\&input=Y3ZwYlBHU3thcmtnX2d2enJfVid5eV9nZWxfMl9lYmhhcWZfYnNfZWJnMTNfR1lwWE9IcVh9) to decrypt it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtUZtsNGIfv\_gtH10g%2F-MWtV8cUnuXN06m7wvyu%2Fimage.png?alt=media\&token=1e1bb63f-0382-4942-9f25-9d05a6d1a85c)

flag: **picoCTF{next\_time\_I'll\_try\_2\_rounds\_of\_rot13\_TLcKBUdK}**

### &#x20;<a href="#mind-you-ps-and-qs" id="mind-you-ps-and-qs"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtUZtsNGIfv\_gtH10g%2F-MWtVLrG73r0stP6lWQb%2Fimage.png?alt=media\&token=b99c55a6-b3fb-419e-9bb1-7fdab88198ac)

It's is the usual RSA challenge.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtUZtsNGIfv\_gtH10g%2F-MWtVT68Vhsqe7JGMOjx%2Fimage.png?alt=media\&token=65e8564f-1cfe-467e-8e6e-40f1101dfcc6)

We have to decrypt it based on the value given. I'm not good at math and just use[ rsactftool](https://github.com/Ganapati/RsaCtfTool) to decrypt it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtUZtsNGIfv\_gtH10g%2F-MWtWlV\_R8OaudiesYMw%2Fimage.png?alt=media\&token=a583c3b7-9a0b-4231-9c97-07ee8a85db62)

flag: **picoCTF{sma11\_N\_n0\_g0od\_23540368}**

### &#x20;<a href="#dacshund-attacks" id="dacshund-attacks"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtUZtsNGIfv\_gtH10g%2F-MWtXCGcL8Y9I0RpFgz3%2Fimage.png?alt=media\&token=a6859e74-95cb-4d25-a1b7-1034f00785ed)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtUZtsNGIfv\_gtH10g%2F-MWtXZVqX\_ZMiGPgqTIn%2Fimage.png?alt=media\&token=789a021e-46ab-471f-a654-10d343fbddd0)

In this challenge we were given e,n and c value. The d value can be calculated by yourself. Based on the challenge we know that d has a small value meaning it is vulnerable to the[ wiener attack](https://en.wikipedia.org/wiki/Wiener's\_attack). We can use rsactftool again to decrypt it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtUZtsNGIfv\_gtH10g%2F-MWtZ4iTRLbPZ9h-usDy%2Fimage.png?alt=media\&token=b0745ba1-3cf2-46f3-b0f8-af1d4b46e985)

Flag: **picoCTF{proving\_wiener\_1146084}**

### &#x20;<a href="#play-nice" id="play-nice"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtoWBdxbgVkn77ZNxU%2F-MWtou11ETTaYHtV1wp7%2Fimage.png?alt=media\&token=faf83d8f-7b32-4272-943d-d04cf047fe07)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtoWBdxbgVkn77ZNxU%2F-MWtpnbuHymU1WIzgfbK%2Fimage.png?alt=media\&token=21176a5e-2ae9-4d1d-989c-cfdc129ae1d4)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtoWBdxbgVkn77ZNxU%2F-MWtpw53LOed5FoyiYYX%2Fimage.png?alt=media\&token=bba23602-cf47-4b62-a98b-d52b0dddc29f)

Enter the plaintext into netcat.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWtoWBdxbgVkn77ZNxU%2F-MWtq1EGjOFiN4CuwmaF%2Fimage.png?alt=media\&token=30d5c70f-f180-4b64-a9ec-d17b2411eccf)

flag: **picoCTF{2e71b99fd3d07af3808f8dff2652ae0e}**

### &#x20;<a href="#reverse-engineering" id="reverse-engineering"></a>

### &#x20;<a href="#transformation" id="transformation"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0GKObZnEKHmhrAbcR%2F-MX0TyG8wemvEoR3pXZE%2Fimage.png?alt=media\&token=578b31a0-abb6-45c0-b7c1-ecd437585c59)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0GKObZnEKHmhrAbcR%2F-MX0U3suX41SSMf2ocUv%2Fimage.png?alt=media\&token=2694c91e-e283-4960-9588-0de24f449491)

Opening the file, it looks some kind of unicode characters. I proceed to use [CyberChef](https://gchq.github.io/CyberChef) magic feature to see if it can decrypt it. By putting picoCTF in the crib, we were able to decode it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0GKObZnEKHmhrAbcR%2F-MX0UWH1plMtkEzj9A-\_%2Fimage.png?alt=media\&token=75eb85dd-e209-4ea4-9d7f-52de31249e81)

**picoCTF{16\_bits\_inst34d\_of\_8\_26684c20}**

### &#x20;<a href="#keygenme-py" id="keygenme-py"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0GKObZnEKHmhrAbcR%2F-MX0UqLv5Wf1B\_al2cJq%2Fimage.png?alt=media\&token=51382e4b-745d-4c08-8d16-4f5cd0211b1d)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0GKObZnEKHmhrAbcR%2F-MX0VPtXfidWXwPsz9Qi%2Fimage.png?alt=media\&token=d9541572-5dc8-4104-b907-dfe521c001a0)

Looking at the source code, we only need to find the key\_part\_dynamic\_1trial part of the flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0GKObZnEKHmhrAbcR%2F-MX0Xh-5HEKd2lUWZfcf%2Fimage.png?alt=media\&token=7c04bf35-19aa-4647-a8fa-63ae52dc3f6f)

Looking at the source, we can see that the dynamic key is taken from the certain value of hexdigest of the username which is GOUGH. We can write a short python script to print it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0GKObZnEKHmhrAbcR%2F-MX0Y-5czOeMMDIBq7hE%2Fimage.png?alt=media\&token=a7c042bc-e310-4eaf-90d6-30023cf13833)

The full flag: **picoCTF{1n7h3|<3y\_of\_f911a486}**

### &#x20;<a href="#crackme" id="crackme"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0Y3kIM\_ZZDs961yDJ%2F-MX0YGn\_wmxPcu5geJT\_%2Fimage.png?alt=media\&token=fac511c8-9a4f-4776-90c4-b6ea8531e364)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0Y3kIM\_ZZDs961yDJ%2F-MX0Yj3nE1xtDsbwiO1Q%2Fimage.png?alt=media\&token=b50bc090-192a-4598-ac5a-d4d157089089)

From the source code, we can see the the program uses ROT47 to encode and decode their bezos\_cc\_secret. We can use [CyberChef](https://gchq.github.io/CyberChef) to decode it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0Y3kIM\_ZZDs961yDJ%2F-MX0Z5Y4V7ssu-x5o3Gr%2Fimage.png?alt=media\&token=512e6dc9-c7aa-4ee9-8c6c-a9766fc7b6ef)

Flag: **picoCTF{1|\\/|\_4\_p34||ut\_4593da8a}.**

### &#x20;<a href="#speeds-and-feeds" id="speeds-and-feeds"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0Y3kIM\_ZZDs961yDJ%2F-MX0ZH3nyRpsE\_QfvAij%2Fimage.png?alt=media\&token=a225738c-1f26-4e2d-ba0c-95fa0e327ba2)

Lets use netcat and save the output.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0Y3kIM\_ZZDs961yDJ%2F-MX0Z\_RMFqaOZhsV0byR%2Fimage.png?alt=media\&token=9c6a1173-1308-4b61-b76c-cd1d5955490d)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0Y3kIM\_ZZDs961yDJ%2F-MX0ZcGuR\_UNtFgBIepa%2Fimage.png?alt=media\&token=ba5bb406-1e46-4947-a3e2-712ac8623845)

From the hint, we know that it is from[ CNC machine](https://www.steckermachine.com/blog/g-code-m-code) which uses G-code as the programming language. After some googling, I found this [https://ncviewer.com/](https://ncviewer.com/) which can be used to plot the G-code language.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0Y3kIM\_ZZDs961yDJ%2F-MX0\_B6gbeUdE6AwkMjk%2Fimage.png?alt=media\&token=cdab1ef4-f9cd-4d46-b3df-f2b2c6007b4b)

flag: **picoCTF{num3r1cal\_c0ntr0l\_f3fea95b}.**

### &#x20;<a href="#shop" id="shop"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0\_KHPz\_VFZabWqPFf%2F-MX0\_\_sslLv8v8mKuoQr%2Fimage.png?alt=media\&token=abd16c5b-81dc-4920-9aa5-7b974a2bdcfa)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0\_KHPz\_VFZabWqPFf%2F-MX0\_pBKYyLzBuP4nnwg%2Fimage.png?alt=media\&token=c17fcb45-f853-4c97-b42a-0a113e0d7853)

In this challenge, we have to exploit the fact that there the programmer did not implement any edge cases in the coin system of the market. We can input any value into the coin such as negative to exploit it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0\_KHPz\_VFZabWqPFf%2F-MX0aDWjR9PRgZuM6eU\_%2Fimage.png?alt=media\&token=12d9965a-d941-4be3-bf96-f6bfee7f4d3e)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0\_KHPz\_VFZabWqPFf%2F-MX0aZS6DrqEAGgh2Wc5%2Fimage.png?alt=media\&token=9c9a618b-cbfb-4bc4-8963-2acc5e6ae2a0)

Flag: **picoCTF{b4d\_brogrammer\_797b292c}**.

### &#x20;<a href="#forensics" id="forensics"></a>

### &#x20;<a href="#information" id="information"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_gQCbHORcncCdlEQl%2F-MW\_n9B6Vylh76zBUjS2%2FScreenshot\_4.png?alt=media\&token=76f76bb8-7fda-4ec9-8304-5a58d78b5349)

In this challenge we were given an image and the hint says something regarding information.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_qVSb5Qdf0JmnHfsU%2F-MW\_rauo-OaNdanFYTbS%2Fcat.jpg?alt=media\&token=4db0ede1-523a-463d-aaaa-3c62e232079b)

So I just try to see the metadata of the image using exiftool.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_gQCbHORcncCdlEQl%2F-MW\_nQycShYUIuYsd7ye%2FScreenshot\_2.png?alt=media\&token=e1ce89c1-7f7a-4ed7-85a0-dca3977fdc8b)

Looking at the license data, it looks like a base 64 string. Lets try decrypting it with [CyberChef](https://gchq.github.io/CyberChef).

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_gQCbHORcncCdlEQl%2F-MW\_niKwpgv-\_2rnluva%2FScreenshot\_3.png?alt=media\&token=dfd66d83-4986-48c8-82ed-84414306f6f4)

And we got the flag **picoCTF{the\_m3tadatais\_modified}.**

### &#x20;<a href="#weird-file" id="weird-file"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_nxI\_l3YEeNS5NeA0%2F-MW\_ouS-eel8dV5yDHxv%2FScreenshot\_5.png?alt=media\&token=ebf79385-f691-47e5-b7f2-72e0cd73ebe6)

In this challenge we were given a Word document with a hint that there are some shell or macro in the file.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_qVSb5Qdf0JmnHfsU%2F-MW\_sBuXPSXXXwHhwJJd%2FScreenshot\_1.png?alt=media\&token=7a9de5ad-287f-4812-85b1-d4dfcfd50b01)

We're also given a youtube [video ](https://www.youtube.com/watch?v=Y7IJjnLGqTQ)that talks about macros in docx file. In the video it shows that we can use[ olevba](https://github.com/decalage2/oletools/wiki/olevba) to extract macros source code from word and ppt files.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_nxI\_l3YEeNS5NeA0%2F-MW\_pZYaLECWDsxvU06p%2FScreenshot\_1.png?alt=media\&token=0b427f8c-0da1-484d-92fa-079fc4bafa57)

From the extracted macros source, we can see that the embedded script is trying to print a line of strings that seems to be encoded in base 64.

$ echo cGljb0NURnttNGNyMHNfcl9kNG5nM3IwdXN9 | base64 -d 1 ⨯

picoCTF{m4cr0s\_r\_d4ng3r0us}

After decoding it, we got the flag **picoCTF{m4cr0s\_r\_d4ng3r0us}**.

### &#x20;<a href="#matryoshka-doll" id="matryoshka-doll"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_qVSb5Qdf0JmnHfsU%2F-MW\_sFnvdD3SuxvDC-QF%2FScreenshot\_3.png?alt=media\&token=78055b3b-bc20-4a16-bb26-7da032792154)

This is matryoshka doll challenge in which we have to extract data from image multiple times to get the flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_qVSb5Qdf0JmnHfsU%2F-MW\_sT4EGspR\_fg1Z6UN%2Fdolls\(1\).jpg?alt=media\&token=f8f9b601-2f84-45c2-94eb-6205d7608d36)

So lets binwalk the image to extract the data a couple times.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_qVSb5Qdf0JmnHfsU%2F-MW\_soksZfhPTOA54Qtr%2FScreenshot\_2.png?alt=media\&token=57b82c45-c14c-4723-beff-42ad3840f7e9)

After a couple times we got the flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_qVSb5Qdf0JmnHfsU%2F-MW\_sv\_dsXBizqO-duvY%2FScreenshot\_4.png?alt=media\&token=0be09d4f-850e-4c58-9f4f-ff8f60ce00fc)

**picoCTF{336cfd51c9d9774fd37196c1d7320ff}.**

### &#x20;<a href="#wireshark-doo-dooo-do-doo..." id="wireshark-doo-dooo-do-doo..."></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_tfzrFzJtegEsab4J%2F-MW\_vMQQ7QNOLmDpsx08%2FScreenshot\_5.png?alt=media\&token=0cdd37c0-a7f3-4819-b1d5-9cee9028d325)

In this challenge we were given a pcap file, lets open it with wireshark.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_tfzrFzJtegEsab4J%2F-MW\_vU0CyEDTDQp5IF-S%2FScreenshot\_1.png?alt=media\&token=a4cc702e-fb05-4179-81cd-6a006cf97776)

I didnt find anything by trying to follow the packet so next I try to export the objects from the pcap.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_tfzrFzJtegEsab4J%2F-MW\_vjFxNXei5RlG-pUS%2FScreenshot\_2.png?alt=media\&token=cd2bcb8d-f492-4174-be68-050ae7d757c3)

Then, I tried opening some of the files and found a string that seems like it has been encoded with Caesar Cipher.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_tfzrFzJtegEsab4J%2F-MW\_w5NieRfL7xpr2tOd%2Fimage.png?alt=media\&token=b1255f9f-b5f7-4e3e-9237-fcc67bc8dad9)

So we can try decoding it either using some website such as [dcode.fr ](https://www.dcode.fr/)or using python script from [github](https://github.com/rhamaa/Caesar-Cipher-Brute-Force/blob/master/caesar\_brute.py):

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_tfzrFzJtegEsab4J%2F-MW\_yH8w-t1i-6Rc35XX%2Fimage.png?alt=media\&token=dc3176df-e23e-4b8c-bdf9-2f9aa339b9af)

The flag is **picoCTF{p33kab00\_**_**1\_s33\_u\_deadbeef}**._

### &#x20;<a href="#macrohard-weakedge" id="macrohard-weakedge"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaJc5xFbgkQHniZh3r%2F-MWaKV7Wa666RDCtjdtW%2FScreenshot\_6.png?alt=media\&token=edf67bff-a072-4173-b297-c54f82f6defe)

At first I thought this challenge was similar to weird file and tried to extract macro data from the file using olevba, however I didnt manage to get any useable output from it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaJc5xFbgkQHniZh3r%2F-MWaKz-lvmrOd39HII8X%2FScreenshot\_4.png?alt=media\&token=3b39b5e6-e95c-4d8f-88b8-63f00d42201b)

Then I remembered that ppt files are just made up from a bunch of files. I performed binwalk on it to extract the data.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaJc5xFbgkQHniZh3r%2F-MWaL9cnObFKmc3Ow6ID%2FScreenshot\_1.png?alt=media\&token=b74f137e-87c6-4d6c-a543-d1a4c8db13b6)

And after scouring around in the files, I manages to get a string that looks like it has been encoded.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaJc5xFbgkQHniZh3r%2F-MWaLGvpb7JR\_2kV6\_n9%2FScreenshot\_2.png?alt=media\&token=3c94827b-ec96-422f-863b-03bba2605d23)

Since caesar cipher didn't work, I just put the strings into CyberChef and it automatically detected that it was from base64 and got the flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaJc5xFbgkQHniZh3r%2F-MWaLZv1g9S7jumU6cZr%2FScreenshot\_3.png?alt=media\&token=b67441cf-6ef7-4660-8ce9-7d0456b36a5b)

flag: **picoCTF{D1d\_u\_kn0w\_ppts\_r\_z1p5}**

### &#x20;<a href="#trivial-flag-transfer-protocol" id="trivial-flag-transfer-protocol"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaUFLCjDO\_XhAI8Mdz%2FScreenshot\_5.png?alt=media\&token=78a10cdd-805f-40c0-85f4-8d08875f4da9)

In this challenge we have to work with a pcap file. The title says something about ftp. As usual lets try opening it in wireshark and export the ftp objects from the pcap.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaUYjERBlkGVRgfQAh%2FScreenshot\_1.png?alt=media\&token=02de4036-b962-42e5-8d78-9dd83135154f)

We manages to get 2 strings files and 3 pictures.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaUkfc71beMGk-46SI%2Fimage.png?alt=media\&token=e14ed9b5-6781-4783-9188-98b704c59a9a)

Seems like it is encoded with caesar cipher. After decoding it, the instruction says:

> TFTPDOESNTENCRYPTOURTRAFFICSOWEMUSTDISGUISEOURFLAGTRANSFER.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN

> IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS

After that, lets open the program.deb

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaVdDzbbHsdq7UJx41%2FScreenshot\_3.png?alt=media\&token=a391bfee-9cbe-48e3-8a50-7840b344a85f)

It seems that one of the image contains a hidden flag and they used [steghide](https://github.com/StefanoDeVuono/steghide) to hid it with the key:DUEDILIGENCE.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaWqBntEe-sgf\_CrsZ%2Fimage.png?alt=media\&token=d50713dd-82ab-46f9-81ef-744f0bc2919e)

After trying steghide on all 3 pictures, we finally get an output on the third image.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaX7zCkMPpKWhz5y24%2Fimage.png?alt=media\&token=15c32248-d6de-4285-a4da-2ed936d886ef)

flag: **picoCTF{h1dd3n\_1n\_pLa1n\_51GHT\_18375919}**

### &#x20;<a href="#wireshark-two-twooo-two-twoo-.." id="wireshark-two-twooo-two-twoo-.."></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaXQCtWXmxJ8calXzQ%2Fimage.png?alt=media\&token=aea1cf96-3102-4b08-a1d0-5dee9c7a7694)

This challenge was quite guessy and time consuming. We were given a pcap file. However after trying the usual follow packets and export objects, I only found fake flags. I saw someone mentions using NetworkMiner in the discord server and tried it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaY4bMi21jKp7OA\_Go%2F1.png?alt=media\&token=39f9c7ad-2205-44ed-9cdf-ac9a57433a2c)

After some times of taking a look at how it categorize each packets, I noticed something weird at the server and ip ttl value of some packets.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaYd2kSSy3GXMaCemI%2F7.png?alt=media\&token=80af0661-9158-4cd4-86d4-28eb33124e31)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaY\_I8V0IeJBW\_2k8g%2F3.png?alt=media\&token=50ee06b1-482b-4c7e-9b60-16c515a18ac7)

However after decoding it to base64 and submitting, it seems that it was a fake flag such as suggested by the site name itself.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaZaddq-MC2vrAFr49%2Fsa.png?alt=media\&token=11a1c099-b494-4a1b-b3b7-ac24a1b92369)

Then I take a look back at the packets and notice that before the website, each of the packets have a different strings that looks like a base64 encoded strings. I then tried to decode one of the strings.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWaZtvdEWLp\_MEDOwgP%2F6.png?alt=media\&token=d3c7d29d-8cd0-47ae-8e65-1337607f539c)

And indeed it produce part of the flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaLeQ8w5eq9wbPVd41%2F-MWa\_-5-ghZTiDElqOVi%2F9.png?alt=media\&token=fd20ed78-f003-4573-9d42-b155304798fe)

After collecting all of the strings from the packets, we got the flag. **picoCTF{dns\_3xf1l\_ftw\_deadbeef}.**

### &#x20;<a href="#disk-disk-sleuth-ii" id="disk-disk-sleuth-ii"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_gQCbHORcncCdlEQl%2F-MW\_iwcyPQ-tSbx9npeC%2FScreenshot\_4.png?alt=media\&token=46d8f321-6fcc-4a34-bb1c-e0774c7013b3)

The challenge gave us an image that can be mounted with a hint that the flag is stored a file called 'down-at-the-bottom.txt'. Rather than using sleuthkit as suggested, I just use binwalk to extract all the files in the image and find the file with the flag manually.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_gQCbHORcncCdlEQl%2F-MW\_jrTdGvAzlN6K-ASr%2FScreenshot\_2.png?alt=media\&token=40ee5ea5-d9e0-4cc8-802d-03478b59e472)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MW\_gQCbHORcncCdlEQl%2F-MW\_jzYmXKbJ0HGTOkX1%2FScreenshot\_3.png?alt=media\&token=0abaa939-205e-49ee-b1db-8441cdb911ed)

Manages to found the flag file in the root directory. The flag is **picoCTF{f0r3ns1c4t0rn0v1c30ba8d02d}.**

### &#x20;<a href="#milkslap" id="milkslap"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaFezlCyVJIsLlSF\_U%2F-MWaGMvqzFQP65gn9Oly%2FScreenshot\_3.png?alt=media\&token=ae1395e3-430f-4236-bd7f-45f8d4b3c34b)

This was rather a stego challenge. We were given a link to a website and it looks like a script has been made to produce an output of gif from several images.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaFezlCyVJIsLlSF\_U%2F-MWaGcFAjEfT7h07r7rL%2FScreenshot\_1.png?alt=media\&token=7b9c9138-9637-4f3a-a672-98897887ae1c)

After saving the image, I started performing the usual ctf tools: strings, stegsolve, binwalk and view hex. And then after using [zsteg](https://github.com/zed-0xff/zsteg), we manages to get output of the flag from one of the lsb.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWaFezlCyVJIsLlSF\_U%2F-MWaH4vpKN5bmBfnABzv%2FScreenshot\_2.png?alt=media\&token=ca0f6caa-ea5b-4644-96ea-ce2e674a8dab)

The flag is **picoCTF{imag3\_m4n1pul4t10n\_sl4p5}.**

### &#x20;<a href="#tunn3l-v1s1on" id="tunn3l-v1s1on"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWa3tiJqvSPVVUepa6A%2F-MWaCcmjSABKEFVWlCZm%2FScreenshot\_5.png?alt=media\&token=1b7f425b-5054-467f-8b8d-47186b62e0f0)

This was rather a quite hard and guessy challenge for me. In this challenge we were give a file. After looking at the header I was able to determine that it was a .bmp image.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWa3tiJqvSPVVUepa6A%2F-MWaCwl0wAFNVo95lBql%2FScreenshot\_2.png?alt=media\&token=4998a5c7-4cd9-4a8f-ae2a-0751b6d3ca4c)

I then proceed to try opening the image using image magick display since windows program was unable to open it directly.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWa3tiJqvSPVVUepa6A%2F-MWaD7NVnaVapPLKqsLp%2FScreenshot\_1.png?alt=media\&token=6d3bd805-5c61-4781-8049-484c14c1a5ba)

From the displayed image, we can guess that this image hex value has been altered and not showing the whole picture.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWa3tiJqvSPVVUepa6A%2F-MWaEGVXwysX7fZWgKDL%2Fimage.png?alt=media\&token=1e7dee5c-651c-493f-b38b-b2e065c19850)

After some times of reading the bitmap information from this[ website](http://www.ece.ualberta.ca/\~elliott/ee552/studentAppNotes/2003\_w/misc/bmp\_file\_format/bmp\_file\_format.htm), I started to try and change the hex value of the image. After several days of break and taking a look back, I was able to produce the full image though the colors are not fully correct by changing these offset: 00Ah, 0012h and 0016h.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWa3tiJqvSPVVUepa6A%2F-MWaEpsxe-uFKhQSrTkl%2FScreenshot\_3.png?alt=media\&token=d3d16d02-199d-42ab-904b-ed4f1edba35f)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MWa3tiJqvSPVVUepa6A%2F-MWaEvcLxB38Fqo-eIU6%2Fadas.bmp?alt=media\&token=6aca7533-de39-4abd-b6fc-6a95a87edc0b)

The flag is: **picoCTF{qu1t3\_a\_v13w\_2020}.** This challenge taught me a lot about bitmap and how it was actually structured, I do think it deserve more points than most of the forensic challenges.

### &#x20;<a href="#general-skills" id="general-skills"></a>

### &#x20;<a href="#obedient-cat" id="obedient-cat"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX08615Hlske1KzaRqm%2Fimage.png?alt=media\&token=63b2678a-eebf-4d33-aa15-c758cf694ec8)

As the challenge name suggest, just use the cat syntax on the flag file.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX08IDWZA5tn8ZM0K2w%2Fimage.png?alt=media\&token=b684974d-c280-4dfe-8fa5-4d7151673c06)

flag: **picoCTF{s4n1ty\_v3r1f13d\_28e8376d}**

### &#x20;<a href="#python-wrangling" id="python-wrangling"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX08QCnVho7mO7IWuVD%2Fimage.png?alt=media\&token=758fc580-26c1-4e25-94d2-9de5ca01fe8b)

Download the files, and use python to open them: `python3 ende.py -d flag.txt.en`

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX096T8mM7Zp\_q\_196f%2Fimage.png?alt=media\&token=f90ffc85-6da5-4f4a-a8d4-0ffbfcb16a49)

### &#x20;<a href="#wave-a-flag" id="wave-a-flag"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX09GVf6HZTGaThTQb9%2Fimage.png?alt=media\&token=90008119-d454-4674-8b26-752ca18c1cc8)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX09e2ClhOoq77y9vy9%2Fimage.png?alt=media\&token=3aa40afd-bafe-4366-8ad5-c102093a3b82)

It's an executable program, lets change the permision and run it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX09owL-8cfHDJ45gGM%2Fimage.png?alt=media\&token=29f4050a-dc57-4268-bc2c-52a8c7c2407c)

Flag: picoCTF{b1scu1ts\_4nd\_gr4vy\_18788aaa}

### &#x20;<a href="#nice-netcat..." id="nice-netcat..."></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX09vPWs2R-NkC9ERzG%2Fimage.png?alt=media\&token=f050348b-f819-4bf8-b40b-8f1d4a54a1ca)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0A56A9BDJ3cbOgVRH%2Fimage.png?alt=media\&token=ec88ceca-cd09-4f6b-958d-23914f09493a)

It gives numbers as output, let save it into txt.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0ADP6us\_x08KYWCUD%2Fimage.png?alt=media\&token=85db1fe9-8b29-4f33-b92c-fc9ddb8f4706)

Based on the hint, it's from ascii, lets decode it to text with this [website](https://convert.town/ascii-to-text).

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0AeKSEt7pzgL8SvL2%2Fimage.png?alt=media\&token=0637d9ed-bfeb-4b2a-9860-9dea9af13521)

Flag: **picoCTF{g00d\_k1tty!\_n1c3\_k1tty!\_d3dfd6df}**

### &#x20;<a href="#static-aint-always-noise" id="static-aint-always-noise"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0BDYWkheOl77Q1asF%2Fimage.png?alt=media\&token=a3919b2b-0585-4415-862c-bc2e821d70a8)

The static is an exe program, change the permission and run it.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0BcIoj8hsP0tgfUal%2Fimage.png?alt=media\&token=c5d9117a-88d1-40e1-9d33-9b0d31aeb9f1)

Lets see the other file ltdis.sh

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0CagMSTF4Qr2XJQle%2Fimage.png?alt=media\&token=c70e31db-b67c-4e2f-9244-1b394f0570a9)

It seems that this bash script is similar to `objdump` that is used to disassemble elf 64 files.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0D3mSwTlpOOvy5ZK8%2Fimage.png?alt=media\&token=77a6c58c-9a45-4db0-90ba-b755ed2e09ca)

Using `objdump -s` option, gave us the flag.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0DGGV49GiEV4HChBB%2Fimage.png?alt=media\&token=3d684bb2-44ab-4d59-a05a-dde0c5406fd6)

**picoCTF{d15a5m\_t34s3r\_ccb2b43e}.**

### &#x20;<a href="#tab-tab-attack" id="tab-tab-attack"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0DQwsMeXTUNzrRub2%2Fimage.png?alt=media\&token=31973c44-3db0-40df-b359-f8ad13b1aed0)

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0Di8FltcU8dSD7az3%2Fimage.png?alt=media\&token=d8421cc2-28e5-4034-a47e-2ad147d5b311)

Lets use `cat` syntax to open the unzipped file.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0DpAlJkYSPV6T7s1l%2Fimage.png?alt=media\&token=412d38f6-3b05-4a98-b5a0-e20b8264f6eb)

flag: **picoCTF{l3v3l\_up!\_t4k18c}.**

### &#x20;<a href="#magikarp-ground-mission" id="magikarp-ground-mission"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0F8rKj-AGm4jctFxX%2Fimage.png?alt=media\&token=5a08933f-dd0b-4523-aaf7-6d48cd3324ca)

Lets connect to the ssh with the given credentials.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0Fo5H6PkyCXsrl7gM%2Fimage.png?alt=media\&token=e1ae5f18-2007-4179-bf78-0e1f7a98d5dc)

This challenge just taught us to use the basic `ls` and `cd` command in the terminal.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX07nxSuFye6mSYonHL%2F-MX0FzPRzurhUGWcoyvB%2Fimage.png?alt=media\&token=51a70210-acc4-466c-af5b-09dba749e996)

flag: **picoCTF{xxsh\_0ut0f\\/\\/4t3r\_21cac893}**

### &#x20;<a href="#binary-exploitation" id="binary-exploitation"></a>

### &#x20;<a href="#whats-your-input" id="whats-your-input"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0GKObZnEKHmhrAbcR%2F-MX0GwHE4q3xQQeR64jx%2Fimage.png?alt=media\&token=4d30193f-91ef-4a95-8d49-6684a97560d7)

Based on the hint lets see the python version of the file.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0GKObZnEKHmhrAbcR%2F-MX0HI1mvI7HAzuQAIjy%2Fimage.png?alt=media\&token=e5e1b770-b46e-4bdc-9388-6c6d4a6ad024)

It was created with python2 which has vulnerability in the input() function. This is the main reason why people have converted to python3. We can exploit it using `import('os').system("put command here")` in the input.

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0GKObZnEKHmhrAbcR%2F-MX0INnK\_bYHuRHo3r60%2Fimage.png?alt=media\&token=34eda178-12ce-4ed8-833a-a80a7f8c17c7)

flag: **picoCTF{v4lua4bl3\_1npu7\_8433797}**

### &#x20;<a href="#binary-gauntlet-0" id="binary-gauntlet-0"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0GKObZnEKHmhrAbcR%2F-MX0IztxbUxbPv0p2ror%2Fimage.png?alt=media\&token=68da4bca-bb4c-48b6-8d89-a46d5c08f34f)

### &#x20;<a href="#stonks" id="stonks"></a>

![](https://439071065-files.gitbook.io/\~/files/v0/b/gitbook-28427.appspot.com/o/assets%2F-MWEN\_\_ASIV1YRyhrCvN%2F-MX0adnsoW0W\_f8SGWAh%2F-MX0apve4Bmx3iKcvQRu%2Fimage.png?alt=media\&token=5000f0a8-1035-47bd-acc1-03e9492ea4b1)

### &#x20;<a href="#conclusion" id="conclusion"></a>

Overall I really enjoyed the ctf. As a solo player, I was able to learn a lot of things especially in reverse engineering and bin exp. Hopefully I will be able to solve more challenge in the upcoming CTFs.
