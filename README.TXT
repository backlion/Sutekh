# Sutekh
An example rootkit that gives a userland process root permissions
Tested on Linux kernel (Arch Linux) 4.16.5-1-ARCH x86_64, (Debian) 4.9 x86_64

[INSTALL]
1. Install latest Linux headers for your kernel. Example (debian): [apt install linux-headers-$(uname -r)]
2. $ git clone https://github.com/PinkP4nther/Sutekh
3. $ cd Sutekh && make
4. $ gcc getroot.c -o getroot
5. $ sudo insmod sutekh.ko

[Run]
$ ./getroot

[Output example]
$ ./getroot
[+] UID = 0
[+] EUID = 0
[!!!] Popping r00t shell!!!
[root@localhost Sutekh]# id
uid=0(root) ..SNIP..

[Remove]
sudo rmmod sutekh

[Note]
Check dmesg to see LKM output
$ dmesg
[ 9433.780312] [+] UID = 1000
               [+] EUID = 1000
[ 9433.780316] [!] Attempting UID change!
[ 9433.780319] [!] Changes Complete!
