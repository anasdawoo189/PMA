# PMA-CH1-labs

## lab 01-01

### Q1

To upload the malware, I need to get the hashes to get the hashes I will use pestudio.

![hashes](photos/lap1-1hashes.png)

Then I am going to upload it in virustotal.com

![virustotal](photos/lap1-1virustotal.png)

So, U can see that there are 55/71 antivirus signatures. I can get more info from virustotal like

![virustotal1](photos/lap1-1virustotal1.png)

### Q2

To get the compiled date of these filed we will use peview. I will find this info in IMAGE_FILE_HEDER (IMAGE_NT_HEADERS > IMAGE_FILE_HEDER)

![date](photos/lap1-1date.png)

As U can see here it was compiled in 2010/12/19.

### Q3

Here I need to know if this malware is packed or not, I will use peview to check Virtual Size
And Size of Raw Data in IMAGE_SECTION_HEADER.text If they R equal that is means it is not backed.

![packing](photos/lap1-1packing.png)

### Q4

We need to check the imports so I will use pestudio.

![imports](photos/lap1-1imports.png)

Lab01-01.exe

![imports1](photos/lap1-1imprts1.png)

Lab01-01.dll
As U can see their R many imports some of them will give U important info and the rest is not important.
I will use [malapi](https://malapi.io/) to get info about suspicious imports.

* From Lab01-01.exe u can find that:
  * CreateFileMappingA
    from it is name it is creating something  when u open it in malapi it will give u this info "that loads a file into memory and makes it accessible via memory addresses" so u can Guess u will find an ip.
  * FindNextFileA
  * FindFirstFileA
    U can guess from these two functions that the malware is searching in the directories for some reason.
  * CopyFileA
    this functions is copying existing file
* From Lab01-01.exe u can find:
  * CreateProcessA

from these two files we can say that these files r searcing for something and creating something.

### Q5

C:\windows\system32\kerne132.dll u can find that in Lab01-01.dll. u will ask me where is the problem? it supose to be **kernel** not **kerne1**

### Q6

in strings u will find this ip 127.26.152.13

### Q7

i think this malware is downloading files to my machine

## lab 01-02

### Q1

To upload the malware, I need to get the hashes to get the hashes I will use pestudio.

![hashes](photos/lap01-02hashes.png)

Then I am going to upload it in virustotal.com

![virustotal](photos/lap01-02virustotl.png)

 So, U can see that there are 54/70 antivirus signatures. I can get more info from virustotal like

![virustotal](photos/lap01-02virustotal1.png)

### Q2

it is packed file with UPX why?

![packed](photos/lap01-02packed.png)

here u can see that there is upx after sections and headers that is mean it is packed. to unpack it i will use UPX

![unpacking](photos/lap01-02unpacking.png)

### Q3

We need to check the imports so I will use pestudio:

![imports](photos/lap01-02imports.png)

* InternetOpenUrlA
* InternetOpenA
* CreateServiceA
* StartServiceCtrlDispatcherA
  
i think we will find url. this malware is creating something and it is connecting the main thread of the process to the service control manager.

### Q4

we will check strings with pestudio u wil find this URL http^://www.malwareanalysisbook.com

## lab01-03

### Q1

To upload the malware, I need to get the hashes to get the hashes I will use pestudio.

![Alt text](photos/lap01-03hashe.png)

Then I am going to upload it in virustotal.com 

![Alt text](photos/lap01-03virustotal.png)

 So, U can see that there are 60/70 antivirus signatures. I can get more info from virustotal like

 ![Alt text](photos/lap01-03virustotal.png)

### Q2

it is packed file why?

![Alt text](photos/lap01-03packing.png)

virtual size is >>>> size of raw data and we can use peid

![Alt text](photos/lap01-02packedtype.png)

I can say that it is packed with FSG , I can not unpack it now.

### Q3

now i can not

### Q4

now i can not

## lab01-04

### Q1

To upload the malware, I need to get the hashes to get the hashes I will use pestudio.

![hashes](photos/lab01-04hashes.png)

Then I am going to upload it in virustotal.com

![Alt text](photos/lab01-04virustotal.png)

 So, U can see that there are 58/70 antivirus signatures. I can get more info from virustotal like

![Alt text](photos/lap01-04virustotal1.png)

### Q2

no it is not packed why?

![packing](photos/lab01-04packing.png)

because virtual size is nearly equal to size of raw data

### Q3

i well use peview

![Alt text](photos/lab01-04date.png)

it was combiled in 2019/08/30

### Q4

![Alt text](photos/lab01-04imports.png)

important impors:

* WriteFile
* CreateFileA
* MoveFileA
* WinExec
* OpenProcess
i do not knoe but it is creating something.

### Q5

I will try to check strings i found:

* http^://www.practicalmalwareanalysis.com/updater.exe
* \system32\wupdmgrd.exe

### Q6

How to check if there is recource? u can find it in pestudio in resources section

![Alt text](photos/lab01-04resource.png)

and u can find it in peview

![Alt text](photos/peview.png)

To extract it I will use resource hacker action --> save resource to a binary file

![Alt text](photos/lab01-04extract.png)

now i need to analys it. so i need to get it is hash wich is -u can get it from pestudio- 6A95C2F88E0C09A91D69FFB98BC6FCE8 MD5.
Then u can upload it to virustotal:

![Alt text](photos/binaryvirustotal.png)

I need to check imports:

![Alt text](photos/binaryimports.png)

There r some interesting imports:

* URLDownloadToFileA
* WinExec

i think this binary is downloading something so i think i will find a URL. So i need to check strings ,i found:

* http^://www.practicalmalwareanalysis.com/updater.exe
* \system32\wupdmgrd.exe

# PMAT-lab

## Q1

to get the hash i will use pestudio 0C82E654C09C8FD9FDF4899718EFA37670974C9EEC5A8FC18A167F93CEA6EE83

![Alt text](photos/PMATlab1.png)

## Q2

the architecture is 32-bit

![Alt text](photos/PMATarchi.png)

## Q3

![Alt text](photos/PMATvirustotal.png)

U can see that there are 59/70 antivirus signatures. I can get more info from virustotal like

## Q4

i can not get important info from strings section why? because there is too many strings

## Q5

i will check imports there a lot i think it will be hard to get info from it

## Q6

no it is not packed why?

* I can see the hearders

![Alt text](photos/PMATpacking.png)

* virtual size is nearly equal to size of raw data

![Alt text](photos/PMATpacking1.png)