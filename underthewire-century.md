---
description: https://underthewire.tech/century
---

# 🐈⬛ 🐈⬛ 🐈⬛ UnderTheWire Century

### Century 0-1

![](<.gitbook/assets/image (1) (1).png>)

![](<.gitbook/assets/image (42).png>)

![](<.gitbook/assets/image (62).png>)

![](<.gitbook/assets/image (166).png>)

<mark style="color:green;">**century**</mark>

### Century 1-2

Challenge ask us to find build verison of PowerShell instance.&#x20;

![](<.gitbook/assets/image (221).png>)

According to this [microsoft module](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about\_powershell\_editions?view=powershell-7.2), we can list the detail of our PS using `$PSVersionTable` command.

![](<.gitbook/assets/image (172).png>)

<mark style="color:green;">**10.0.14393.4583**</mark>

### Century 2-3

![](<.gitbook/assets/image (150) (2).png>)

![](<.gitbook/assets/image (289).png>)

`Invoke-WebRequest` has the same function as wget command according to [https://linuxhint.com/run-wget-powershell/](https://linuxhint.com/run-wget-powershell/).

<mark style="color:green;">**invoke-webrequest443**</mark>

### Century 3-4

![](<.gitbook/assets/image (127).png>)

We can use `(Get-ChildItem | Measure-Object)`.Count to get the total number of files in a directory.&#x20;

* Get-ChildItem = Equivalent to dir , get the items and child items in a folder or registry key.
* Measure-Object = measure the property of the command. There are various measurement parameters are available. For example, Average, Count, sum, maximum, minimum.
* .Count = to specify output for count only.

![](<.gitbook/assets/image (56).png>)

<mark style="color:green;">**123**</mark>

### Century 4-5

![](<.gitbook/assets/image (228) (1).png>)

CD to the directory either by pressing tab or specify directory name using '\file'.

![](<.gitbook/assets/image (224).png>)

<mark style="color:green;">**5548**</mark>

### Century 5-6

![](<.gitbook/assets/image (146).png>)

According to [PS module](https://docs.microsoft.com/en-us/powershell/module/activedirectory/get-addomain?view=windowsserver2022-ps), we can use `Get-ADDomain -Current LoggedOnUser` to get the domain information for the domain of the currently logged on user.

![](<.gitbook/assets/image (38).png>)

<mark style="color:green;">**underthewire3347**</mark>

### Century 6-7

![](<.gitbook/assets/image (226).png>)

Use option -Directory to only get folders. `(Get-ChildItem -Directory | Measure-Object).Count`&#x20;

![](<.gitbook/assets/image (148).png>)

<mark style="color:green;">**197**</mark>

### Century 7-8

![](<.gitbook/assets/image (98).png>)

Use gci with -Recurse to repeat the command in all subfolder in the directory and specify the file name with -Filter.

![](<.gitbook/assets/image (29).png>)

<mark style="color:green;">**7points**</mark>

### Century 8-9

![](<.gitbook/assets/image (109).png>)

We can use `Get-Unique` which is the equivalent of uniq to get the non repeated words in the file. Then we use `Measure-Object` <mark style="color:green;"></mark> to count the unique entries.

![](<.gitbook/assets/image (176).png>)

<mark style="color:green;">**696**</mark>

### Century 9-10

![](<.gitbook/assets/image (183).png>)

We use [GetContent](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-content?view=powershell-7.2) with [-Delimiter](https://www.mssqltips.com/sqlservertip/5427/parsing-strings-from-delimiters-in-powershell/) " " to split the words into an array and find the 161st word by using Select -Index 160.( Array starts from 0).

![](<.gitbook/assets/image (106).png>)

<mark style="color:green;">pierid</mark>

### Century 10-11

![](<.gitbook/assets/image (229).png>)

According to the answer from StackOverFlow, we can use `Get-WmiObject` cmdlet to get more details and information of a windows 32 service. Then we can use findstr [wuauserv](https://www.windows-commandline.com/start-stop-windows-update-service/)(windows update service) which is the equivalent of grep to get the  details of windows update service.

![](<.gitbook/assets/image (227).png>)

![](<.gitbook/assets/image (147).png>)

<mark style="color:green;">**windowsupdates110**</mark>



### Century 11-12

![](<.gitbook/assets/image (198).png>)

We can use gci -recurse -hidden 2>$null to find any hidden file in a directory.

* hidden = find file with only hidden property.
* 2>$null = discard error.

![](<.gitbook/assets/image (74).png>)

![](<.gitbook/assets/image (211).png>)

<mark style="color:green;">**secret\_sauce**</mark>

### Century 12-13

![](<.gitbook/assets/image (107).png>)

We use [Get-ADDomainController](https://docs.microsoft.com/en-us/powershell/module/activedirectory/get-addomaincontroller?view=windowsserver2022-ps) to get Active Directory domain controllers name.&#x20;

![](<.gitbook/assets/image (104).png>)

After finding the domain controller name, we can use `Get-ADComputer -Identity "UTW" -Properties * | Select Name, Description`  to get the description of our AD name.

* Get-ADComputer = get active directory computer details.
* \-Identity "UTW" = specify our AD name.
* \-Properties \* = list all possible properties.
* Select Name, Description = filter out the only parameter we want.

![](<.gitbook/assets/image (192).png>)

<mark style="color:green;">**i\_authenticate\_things**</mark>

### Century 13-14

![](<.gitbook/assets/image (93).png>)

Use getcontent with Measure-Object -Word to only get words amount.

![](<.gitbook/assets/image (87).png>)

<mark style="color:green;">**755**</mark>

### Century 14-15

![](<.gitbook/assets/image (217).png>)

Use getcontent with -Delimiter to split words into array. Then use findstr ^polo (^to specify whole word only) to grep polo. Lastly use count to count the number of polo words in the file.

![](<.gitbook/assets/image (49).png>)

<mark style="color:green;">**153**</mark>
