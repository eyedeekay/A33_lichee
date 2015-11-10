# Contents of the SDK

The SDK is split into several parts, but the build scripts requires them to be complete.

A33
 |-- android -- android source kitkat 4.4
 |-- lichee
     |-- build.sh -- main build script
     |-- buildroot -- rootfs, toolchain, and build scripts
     |-- linux-3.4 -- linux kernel
     |-- brandy -- boot related stuff
         |-- build.sh -- simple build script for u-boot
         |-- u-boot-2011.09 -- Allwinner's port of u-Boot 
     |-- out -- build intermediaries and results. toolchain is also in here
     |-- tools
         |-- tools_win -- LiveSuit/PhoenixSuit tools and drivers
         |-- pack -- tools and configuration related to firmware packing
             |-- chips -- chip specific files (boot0/u-boot binaries, fex files)
             |-- common -- common config files and tools
             |-- out -- work directory for firmware packing
             |-- pack -- firmware packing script 


# Examples:

1. Build linux-3.4 kernel for redwood, maple, y3

  $cd lichee/
  $./build.sh config
  
All available chips:
   0. sun8iw5p1
Choice: 0

All available platforms:
   0. android
   1. dragonboard
   2. linux
Choice: 0

All available kernel:
   0. linux-3.4
Choice: 0

All available boards:
   0. evb
   1. maple
   2. redwood
   3. y2
   4. y3
Choice: <select your board>

2. Build android source

$ cd android/
$ . build/envsetup.sh
$ lunch <your device>
$ make -j4

$ export ANDROID_IMAGE_OUT=/home/<user>/A33/android/out/target/product/<your device>

$./build.sh pack


