Hello, I thought about creating video series about pmos how to port it to Nokia 1 plus, and I would like to ask for your opinions on what topics should I cover.

Each number would be one video (I also want to add subtitles)

###Basics:

1. introduction
    * what pmos is/isn't
    * brief comparison with Android/other distros
    * requirements
2. Acquiring info
    * is bootloader even unlockable?
        * don't update system, sometimes vendor locks bootloader in update
    * finding kernel source code
    * how to create wiki page for user, device and edit it to contain all found data
    * enabling USB debugging, `adb shell`, mentioning that root is nice here
        * `getprop`
            * `getprop ro.product.device` usually have device codename
        * cat /proc/cpuinfo
        * uname -a
3. Acquiring info - mainline edition
    * internal photos on [https://fccid.io/](https://fccid.io/)
    * disassembly
        * noting part numbers
        * finding UART
    * photos on iFixIt
    * [Tuning sysfs](https://wiki.postmarketos.org/wiki/Tuning_sysfs)
        * can be done if root access exists
        * can be stuck on some files, how to fix it (kill, if/continue in script)
4. Basic port
    * installing pmbootstrap and using it
    * editing device and Linux packages
    * compile, make .patch files and repeat 
    * try to boot
    * where to find logs and put them (pastebin), Matrix/IRC room communication
    * testing what works and updating wiki
5. Publishing port
    * git basics
    * push request
    * create fork
    * `git add remote...`
    * `git commit`, `push`
    * creating merge request and applying requested changes

###Functions:
I thought about talking how to do that in downstream kernel if possible and add info about upstream, basically have two parts for each video (down- and upstream)

1. Basics
    * USB networking
    * screen
    * touchscreen
    * flashing
2. Wi-Fi
3. FDE
4. Battery
5. 3D (only upstream part)
6. everything else from the devices table

###Mainline
I've never mainlined, I don't really know how to organize this or even if I get that far:
How about organizing mainline like this:

1. Introduction
    * What mainline is
    * how user can prepare and get mainline kernel to a point where some kind of output can be obtained
    * trying to get anything on downstream kernel to make sure one of these methods work
        * UART
        * Ramoops/last-kmsg method
2. mainlining when dtb/dtbi files are available
    * getting data from mainstream kernel using UART/ramoops/last-kmsg
3. adding more devices  
    * USB networking, screen..., everything

maybe in the future:

1. how to make dtb/dtbi files (and mainline) when only board files are available

###Optional:
things not covered in other videos that still may be useful:

2. postmarketOS friends
    * comparison and info about other distros, mention [TuxPhones](https://tuxphones.com/)
    * Rockbox, OpenWRT etc.?
3. DE comparison
4. popular problems with boot (backlight set to 0, etc.)