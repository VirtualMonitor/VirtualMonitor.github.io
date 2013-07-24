---
layout: post
title: Build Instructions
---
[Build on windows](#Build on windows)
[Build on Linux](#Build on Linux)

### Build on windows ###
#### Windows build prerequisites ####
1. Install Visual C++ 2010 Express. if you have full edition, that is great. or you can download free Express edition.
[http://www.microsoft.com/express/downloads](http://www.microsoft.com/express/downloads)

2. Microsoft .NET Framework 4
[http://www.microsoft.com/en-us/download/details.aspx?id=17718](http://www.microsoft.com/en-us/download/details.aspx?id=17718)

3. Windows Platform SDK v7.1 
[http://www.microsoft.com/en-us/download/details.aspx?id=8279](http://www.microsoft.com/en-us/download/details.aspx?id=8279)

4. Windows Driver Development Kit (WDK) v7.1. 
[http://www.microsoft.com/en-us/download/details.aspx?displaylang=en&id=11800](http://www.microsoft.com/en-us/download/details.aspx?displaylang=en&id=11800)

5. Install Microsoft Visual C++ 2010 Service Pack 1
[http://www.microsoft.com/downloads/en/details.aspx?FamilyID=689655b4-c55d-4f9b-9665-2c547e637b70](http://www.microsoft.com/downloads/en/details.aspx?FamilyID=689655b4-c55d-4f9b-9665-2c547e637b70)

6. Install Microsoft Visual Studio 2010 Service Pack 1. 
[http://www.microsoft.com/downloads/en/details.aspx?FamilyID=75568aa6-8107-475d-948a-ef22627e57a5](http://www.microsoft.com/downloads/en/details.aspx?FamilyID=75568aa6-8107-475d-948a-ef22627e57a5)

7. LibJpeg-turbo, I am using 1.3. download libjpeg-turbo-1.3.0-vc64.exe for 64bit, libjpeg-turbo-1.3.0-vc.exe for 32bit.
[http://sourceforge.net/projects/libjpeg-turbo/files](http://sourceforge.net/projects/libjpeg-turbo/files)

#### Windows build ####
1. Change to the root directory and execute our configure script to setup your build environment(suppose libjpeg-turbo installed to c:\libjpeg-turbo): cscript configure.vbs --with-libjpeg=c:\libjpeg-turbo 

2. Change to the root directory of the sources and enter our build shell environment: env.bat 

3. To build a release package, type kmk. This produces the binaries in out\win.x86\release\bin. If you want to build a debug version, enter kmk KBUILD_TYPE=debug. if you want build 64bit version. enter kmk KBUILD_TARGET=amd64


### Build on Linux ###
