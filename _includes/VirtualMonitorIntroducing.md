VirtualMonitor 0.2.0 Beta released 
Goto <a href="https://github.com/VirtualMonitor/VirtualMonitor/releases" target="_blank"> Download</a> Pre-Compiled binary files.

1. Support Windows 2000 to Windows 7. when you run virtual monitor on windows7, it will disable Aero Glass automatically, and it will be enable when virtual monitor exit.
2. You can install or remove Driver with a simple command. Run WinDrvInstaller.exe -i for installing. WinDrvInstaller.exe -u for removing.
3. Support both 32bit and 64bit.
4. test mode support for developer. 
	* if you want do some enhancement for VNC part of VirtualMonitor. you do not care the driver, you can run VirtualMonitor with -dummy. the it will generate generate some random dirty pixels data. then you can debugging it.
	* if you want implement a driver on a new OS platform, e.g. Linux. Then fisrt step, you just focus on how to implement the driver, and dump out the frame buffer to a file. then you can run VirtualMonitor with -tf filename. To check your driver is work or not. once it works. it is easy make it works with virtualMonitor. you can download an example ScreenRawCap.bin file <a href="images/ScreenRawCap.bin" target="_blank"> here </a>. then you run virtualmonitor -tf ScreenRawCap.bin. it is 800x600x32.


## What is VirtualMonitor ##
VirtualMonitor is a cross-platform opensource software, it allows you to use compute, tablet, smartphone as a second monitor for your primary computer. The following snapshot is an example of using IPad as a second monitor. 
![Ipad As 2nd Monitor](/images/IpadAs2ndMonitor.png "Ipad As 2nd Monitor")

No extra app needed on your IPad. just run your web browser with HTLM5 support or with Java applet support. So it can be used to support many devices easily.

 VirtualMonitor consists following components:

### Kernel mode driver ###

Kernel mode driver will Create a Virtual Monitor device in Operating System, it act as a real monitor, it receving pixels content from OS,
then save those pixels to it own framebuffer. 
Driver is a OS dependent component. We have to write diferent driver for diferent OS.
currently, There is only XPDM driver implemented for windows.

### User mode daemon ###
User mode daemon consists two major components:

1. Driver interface. Comunicate with driver, to read dirty pixels, change resolution. etc.
2. VNC Server comunicate with "VNC Client", update those dirty pixels data to those device. VirtualMonitor use [libvncserver](http://libvncserver.sourceforge.net)

Cross-platform is one of the aim of VirtualMonitor. Driver and Driver interface which comunicate to User mode daemon are platform dependent, but all of other code are platform independent. Curently, only a XPDM driver implemented for windows, If you run VirtualMonitor on Linux. there is no VirtualMonitor driver. "Dummy" driver interface will handle this case. It will not comunicate with real driver, it just generate some random dirty pixels data. it works like this: 

![VirtualMonitor On Linux](/images/VirtualMonitorOnLinux.png "VirtualMonitor On Linux")

If you look into Dummy Driver interface, you will found it has only few codes and very easy to understand. The purpose of Dummy Driver interface is: Provide a skeleton to show how to comunicate with user mode daemon. So if you want to develop a VirtualMonitor driver for Linux or other platform, then you can focus on the driver side, once your driver works, you can integrate your driver to VirtualMonitor based on Dummy Driver interface. 

VirtualMonitor is still in the development stage, the source code is based on [VirtualBox](http://www.virtualbox.org). Why using [VirtualBox](http://www.virtualbox.org). it is great cross-platform opensource software. right now I am only one developper. I have to reuse opensource as possible as I can. And also I hope I can contribute to opensource. VirtualBox has some Guest Addition drivers, one of them is display driver. this driver will create virtual display adapter. When guest OS request to draw something on screen. this driver will store the content. and update dirty pixels data through Guest Host Share Memory Mechanism. I ported this driver works on host OS. and send out dirty pixels to another device through network. right now, still lots of unused code in the source tree. I will cleanup later.

If anyone interesting in VirtualMonitor, Please join me. lets develop a usefull cross-platform opensource software.

1. Develop WDDM driver for Windows 7, Windows 8. Current XPDM can work on Windows 7 with Non-Aero mode, the Aero Glass interface will not working. I tested it on  32bit version windows7, it is works. for 64bit window7, it isn't work, as we didn't have driver signature. windows will refuse to run this driver.
2. Develop driver for Linux
3. Current code only support 1 client. Change VNCDisplay.cpp to support mutiple client.
4. enhance current XPDM driver, Create mutiple Virtual Monitor Object, then we can extend destop to more than 1 device. VideoPortCreateSecondaryDisplay
5. Build a Installer(.msi file) for Windows. and automatic install driver.
6. Sign XPDM. hope [ReactOS](http://reactos.org) can help on this.
7. Testing, report and fix bugs,
8. Make VirtualMonitor works with USB, not through networking. Using [LibUSB](http://www.libusb.org/)?
9. Any other idea or suggestion.
10. code cleanup
