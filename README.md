Linux-Realtek-rtlwifi-drivers
===========
### A repo for the newest Realtek rtlwifi codes.

This code will build on any kernel 4.2 and newer as long as the distro has not modified
any of the kernel APIs. IF YOU RUN UBUNTU, YOU CAN BE ASSURED THAT THE APIs HAVE CHANGED.

TO INSTALL:
  
$ sudo apt update && sudo apt install git dkms

cd Downloads

$ git clone https://github.com/alphaspear/Linux-Realtek-rtlwifi-drivers.git<br/>
unofficial<br/>
$ cd Linux-Realtek-rtlwifi-drivers<br/>
<br/>
Now, either you can run:<br/>
$ /Downloads/Linux-Realtek-rtlwifi-drivers<br/>
$ make <br/>
$ /Downloads/Linux-Realtek-rtlwifi-drivers<br/>
$ sudo make install<br/>
<br/>
OR use dkms to build and manage the modules:<br/>
<br/>
<br/>$ /Downloads/Linux-Realtek-rtlwifi-drivers
<br/>$ sudo dkms add ../rtlwifi_new
<br/>$ sudo dkms build rtlwifi-new/0.6 
<br/>$ sudo dkms install rtlwifi-new/0.6
<br/>$ sudo modprobe -v rtl8723de ant_sel=2
 
  <br/>
IF YOU HAVE SIGNAL STRENGTH ISSUES
  <br/>
$ sudo /bin/sh -c 'echo "options rtl8723de ant_sel=2" >> /etc/modprobe.d/rtl8723de.conf'<br/>
OR<br/>
go to the directory with name of your card and edit sw.c
<br/>
In sw.c change .ant_sel = 0 to .ant_sel = 2
  <br/><br/>
Remember, this MUST be done whenever you get a new kernel - no exceptions.<br/>
<br/><br/>
These drivers will not build for kernels older than 4.14. If you are using a kernel newer than 5.2,
I suggest that you use the driver built into the kernel!
