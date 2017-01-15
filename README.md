#Netatalk 2.2.5-2 installation guide for Ubuntu 12.04 LTS  - 16.04 LTS (Precise - Xenial)

First of all, you can ask me "Why?". I've running Ubuntu 12.04 LTS (Precise) on my home-server and I'm a bit lazy to update it for newest release. Also, I have OS X El Capital installed on my laptop (Hackintosh) and an iMac at the office. Somebody can say: "you should buy the Time Capsule", but as I mentioned there is a home-server with Linux and all the things needed was invented before us. 
[Netatalk](http://netatalk.sourceforge.net/) provides support of the AppleTalk protocol stack for Linux. The latest Netatalk version available for Precise via apt is too old  - **2.2.1**.  

    # apt-cache policy  netatalk
```netatalk:
  Installed: 2.2.5-2
  Candidate: 2.2.5-2
  Version table:
 *** 2.2.5-2 0
        100 /var/lib/dpkg/status
     2.2.1-1 0
        500 http://ru.archive.ubuntu.com/ubuntu/ precise/universe amd64 Packages
```
Actual sources of the **3.1.10**  version are currently available at the SourceForge and "debianized" version **2.2.5-2** can be found at the [Launchpad](https://launchpad.net/ubuntu/+source/netatalk). In my case, I want to build ***.deb** package from "debianized" sources available for **Zesty**. All we needed is to fix build dependencies at the **debian/control** file. Why? Because of the package names changes between Ubuntu releases and **licensecheck** has been moved from **devscripts** (Xenial and early) to it's own separate  **licensecheck** package (Yakkety and above).