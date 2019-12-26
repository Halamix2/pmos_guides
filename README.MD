Video Guides
===
topics for guides are in `what.md`, test dir contains some videos from camera for test, `basics` should contain video source/project files if they exist  
[Original Reddit thread](https://www.reddit.com/r/postmarketOS/comments/cpvyx3/creating_video_guides/)

`beamerthemepmos_modified.sty` is a modified verion of `beamerthemepmos.sty` from [artwork repository](https://gitlab.com/postmarketOS/artwork/tree/master/presentation/latex)

---
##some converstions that might be useful for the videos and I don't want to lose:

###What is Halium and libhybris

by Alexeymin:

libhybris is a library that allows loading android-bionic libc based libs into your glibc-based process
libhybris actually provides a set of proxy-libraries, like libEGL.so (instead of mesa's libEGL.so) that in turn internally load android-specific library
for example from /system/lib/egl/libEGL_adreno.so
and proxies all EGL API calls to it

so: libhybris is just a tricky library that contains android dynamic linker implementation inside

Halium is a solution that allows to run stripped version of android (only core services, without all Java and graphics) inside an lxc container to lock it from all unneeded access

so you can combine 2 things: 
you can run core android inside a container, so that vendor-specific binaries can initialize all the hardware like it was made to run by manufacturer
and you can load android hw adaptation libs using libhybris into your linux processes to control that hardware

SailfishOS for example runs core Android services in the same root filesystem with Linux (without container), because all android is mostly located in /system directory and does not clash with linux standard dirs