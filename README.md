# LS720V8_ANDROID_SOURCE

1. Android build
  - Download original android source code ( Jelly Bean 4.1.1_r1 ) from http://source.android.com
  - Unzip opensource packages of LS720_JB_android.tar.gz into downloaded android source directory 
  - And, merge the source into the android source code(JellyBean)
  - Replace vendor folder to other space
  - Run following scripts to build android
    $ source ./build/envsetup.sh
    $ choosecombo 1 generic user
    $ make
  - When you compile the android source code, you have to add google original prebuilt source(toolchain)
    into the android folder
  - After build, you can find output at out/target/product/generic
  - move back vendor to where it was and follow README inside vendor to apply rest of them

2. Kernel Build
  - Unzip LS720_JB_kernel.tar.gz at the android folder
  - When you compile the kernel source code, you have to add google original prebuilt source(toolchain) 
     into the android folder.
    $ source ./build/envsetup.sh
    $ choosecombo 1 generic user
  - Build kernel
    $ cd Kernel
    $ make fx3_spcs_defconfig  ARCH=arm CROSS_COMPILE=arm-eabi-
    $ make ARCH=arm CROSS_COMPILE=arm-eabi-
  - After Build, You Can find the build image at arch/arm/boot
