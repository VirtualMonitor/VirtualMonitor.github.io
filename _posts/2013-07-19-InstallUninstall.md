---
layout: post
title: Install & Uninstall 
---
For 0.2.0 Beta, Open a command shell, 

1. WinDrvInstaller.exe -i for installing.
2. WinDrvInstaller.exe -u for removing.

If you are using Windows vista/Windows7, make sure "Run as administrator"

![Run As administrator](/images/RunAsAdmin.png "Run As administrator")

For 32bit version, we did not sign the driver, please ignore signature warning, just click "Continue Anyway".

![ignore](/images/Install_Step11.PNG "ignore signature warning")

For 64bit version, Windows will refuse to load and run the driver without signature. and fortunately [ReactOS](https://www.reactos.org/) can help us sign the 64bit version.

<!--
[Install Driver on windows XP or later](#InstallDriverOnWindows)

[Install Driver on 2000](#InstallDriverOnWindows2000)

[Driver Uninstall on windows](#Remove)

### <a name="InstallDriverOnWindows"></a>
#### Run WinDrvInstaller.exe, for Windows 7 you have to Run as administrator ####

### <a name="InstallDriverOnWindows1"></a>
![Click Have Disk](/images/Install_Step6.PNG "Click Have Disk")

#### Browser to location of VirtualMonitor.inf ####

![Open VirtualMonitor.inf](/images/Install_Step7.PNG "Open VirtualMonitor.inf")

#### Click Ok ####

![Click OK](/images/Install_Step8.PNG "Click OK")

#### Next ####

![Next](/images/Install_Step9.PNG "Next")

#### Next ####

![Next2](/images/Install_Step10.PNG "Next")

#### ignore signature warning ####

![ignore](/images/Install_Step11.PNG "ignore signature warning")


[Install Driver on windows 2000](#InstallDriverOnWindows2000)

### <a name="InstallDriverOnWindows2000"></a>
#### Start -> run, enter hdwwiz.cpl ####

![hdwwiz.cpl](/images/Install_Step1.PNG "hdwwiz.cpl")

#### choose yes I have already connected the hardware ####

![Connected](/images/Install_Step2.PNG "Connected")

#### selecte Add a new hardware device, then next ####

![new hardware](/images/Install_Step3.PNG "new hardware device")

#### selecte Install the hardware that i manually selecte from a list(Advanced), then next ####

![manual install](/images/Install_Step4.PNG "manual install")

#### selecte display adapter, then next ####

![Display Adapter](/images/Install_Step5.PNG "Display Adapter")

#### following the rest of step  [next step](#InstallDriverOnWindows1) ####

#### Driver Uninstall ####
### <a name="Remove"></a>
#### Right click on My Computer, Choose manage ####

![Manage](/images/Remove_Step1.PNG "computer manage")

#### Choose Device Manager -> Display adapters -> VirtualMonitor Graphics Adapter, right click -> Uninstall ####

![Uninstall](/images/Remove_Step2.PNG "Uninstall")
-->

