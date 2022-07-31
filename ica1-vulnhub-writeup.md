---
description: >-
  ICA:1 is a vulnhub machine available at
  https://www.vulnhub.com/entry/ica-1,748/.
---

# 🦨 ICA1 Vulnhub Writeup

![](<.gitbook/assets/image (169).png>)

Starting the ICA1 box willl greet us with a login page with details of the box ip address. Then, we go to our attack vm and use nmap to scan for open ports at that ip address.&#x20;

![](<.gitbook/assets/image (165).png>)

From the nmap scan, we can see three open ports which are ssh, http and mysql. Since we dont have any details about ssh and mysql, we can visit the http website first.

![](<.gitbook/assets/image (54) (1).png>)

It seems that the website is an older version of [qdPM](https://qdpm.net/), a free open source web-based project management tool. Searching for qdPM 9.2 gave us results of an information disclosure exploit where anyone can access the website database login details by going to http://\<target>/core/config.databases.yml.

![](<.gitbook/assets/image (152).png>)

Accessing the directory presents us with a databases.yml file. The connection and login details of website database was stored in that file.

![](<.gitbook/assets/image (142).png>)

![](<.gitbook/assets/image (91).png>)

From these details, we can login to the mysql database of the website. It seems that there are multiple database available in the mysql. Since I failed to find any important information in qdpm database, I proceed to use another database which is staff.



![](<.gitbook/assets/image (219).png>)

In staff database, I was able to get user information and password id that has been encrypted with base64. Considering there is no email in the names, it seems that it might be used for ssh login.&#x20;

![](<.gitbook/assets/image (284).png>)

Since we does not know which password are for each users, we can use [hydra](https://www.kali.org/tools/hydra/), a powerful login cracker to brute force the ssh login. After decrypting all passwords, we save them into a file called pass.txt along with a file called user.txt.

![](<.gitbook/assets/image (239).png>)

![](<.gitbook/assets/image (162).png>)

Then we can use command `hydra -L username.txt -P pass.txt 192.168.56.103 ssh` to start the brute force process. The results gave us two credentials for the ssh login.

![](<.gitbook/assets/image (25).png>)

First, I tried to login as travis and was able to get the user flag.

![](<.gitbook/assets/image (274).png>)

Then I proceed to login as dexter and found a file called note.txt. The file stated that there is a vulnerable exploit in the system with a hint that the executable files are partially viewable.&#x20;

![](<.gitbook/assets/image (84).png>)

Then I proceed to search for any executable setuid in the server using command  find / -perm -u=s -type f 2>dev/null.&#x20;

* \-perm is used to specify we are searching for files that hve permission.
* \-u=s specify we're looking for files owned by root.
* and 2>dev/null is used to discard any errors.

![](<.gitbook/assets/image (135).png>)

From the results, we can see a file called get\_access which seems to be the source of exploit. However when we ran the get\_access executable setuid, it seems to not works and displays an error message.

![](<.gitbook/assets/image (223).png>)

Since the hint mentions that we can partially view the executables, we tried to run strings on the file.

![](<.gitbook/assets/image (277).png>)

From what we can see here, we can understand how the setuid executable works. It used cat command onto a file in root directory to display the error message. From that details, we can use a setuid priviledge escalation exploit which is known as [path injection](https://blog.creekorful.org/2020/09/setuid-privilege-escalation/). Simply the steps are:

1. &#x20;Create a new file with name cat that will override the original cat file and open a shell when executed by root.
2. Change permission to ensure everyone have rw access to file.
3. Add the directory to $PATH.
4. Run setuid executable.

![](<.gitbook/assets/image (208).png>)

After getting the root privilege, we can get the root flag by going to /root.
