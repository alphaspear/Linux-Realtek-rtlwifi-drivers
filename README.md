Linux-Realtek-rtlwifi-drivers
===========
### A repo for the newest Realtek rtlwifi codes.

This code will build on any kernel 4.2 and newer as long as the distro has not modified
any of the kernel APIs. IF YOU RUN UBUNTU, YOU CAN BE ASSURED THAT THE APIs HAVE CHANGED.

TO INSTALL:
  
:~$ sudo apt update && sudo apt install git dkms

cd Downloads

:~$ git clone https://github.com/alphaspear/Linux-Realtek-rtlwifi-drivers.git
unofficial
:~$ cd Linux-Realtek-rtlwifi-drivers

Now, either you can run:
:~/Downloads/Linux-Realtek-rtlwifi-drivers$ make 
:~/Downloads/Linux-Realtek-rtlwifi-drivers$ sudo make install

OR use dkms to build and manage the modules:

:~/Downloads/Linux-Realtek-rtlwifi-drivers$ sudo dkms add ../rtlwifi_new
:~/Downloads/Linux-Realtek-rtlwifi-drivers$ sudo dkms build rtlwifi-new/0.6 
:~/Downloads/Linux-Realtek-rtlwifi-drivers$ sudo dkms install rtlwifi-new/0.6
:~/Downloads/Linux-Realtek-rtlwifi-drivers$ sudo modprobe -v rtl8723de ant_sel=2
 
  
IF YOU HAVE SIGNAL STRENGTH ISSUES
  
sudo /bin/sh -c 'echo "options rtl8723de ant_sel=2" >> /etc/modprobe.d/rtl8723de.conf'
OR
go to the directory with name of your card and edit sw.c

In sw.c change .ant_sel = 0 to .ant_sel = 2
  
Remember, this MUST be done whenever you get a new kernel - no exceptions.

These drivers will not build for kernels older than 4.14. If you are using a kernel newer than 5.2,
I suggest that you use the driver built into the kernel!
