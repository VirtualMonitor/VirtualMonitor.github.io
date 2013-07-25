---
layout: post
title: Run VirtualMonitor
---
After you installed driver, you can Run VirtualMonitor. open a command line, change to out/win.x86/release/bin/ directory, enter virtualmonitor.exe. it will create a monitor 800x600x32 by default. currently only support 32bit true color mode. but you can change to any resolution if you want. e.g. with argument -x 200 -y 100, then the resolution is: 200x100x32. the following argument are avalible.

 ```
-x x resolution
-y y resolution
-a4 listen on specified ipv4 address
-p4 listen on specified ipv4 port
-a6 listen on specified ipv6 address
-p6 listen on specified ipv6 port
 ```

Once you run it successful, you will get following output. 

 ```
\\.\DISPLAY2
Probe XPDM Display Driver Successful
Update Registry on device mode: Change Successful
Raw dynamic mode change on device mode: Change Successful
24/07/2013 14:50:48 Autoprobing TCP port
24/07/2013 14:50:48 Autoprobing selected TCP port 5900
24/07/2013 14:50:48 Autoprobing TCP6 port
24/07/2013 14:50:48 Autoprobing selected TCP6 port 5900
24/07/2013 14:50:48 Listening for HTTP connections on TCP port 5800
24/07/2013 14:50:48   URL http://ComputerName:5800
24/07/2013 14:50:48 Listening for HTTP connections on TCP6 port 5800
24/07/2013 14:50:48   URL http://ComputerName:5800
Create VNC Display Successful
1 Display Intf Object
 ```

Then you can open web browser with HTML support on your device. connect to: http://ip:5800, then you will see a page:
If the above Java applet does not work, you can also try the new JavaScript-only noVNC viewer. You will need a HTML5-capable browser though. 
Then click the button "Click here to connect using noVNC".
