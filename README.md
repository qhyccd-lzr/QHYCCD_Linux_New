# QHYCCD_Linux_New
This QHYCCD SDK repository contains targz files supporting Intel 64 bit Ubuntu Linux and ARM V8 processors. 
The Linux version was tested on Intel Core I5 & I7 processors. The ARM version was tested with Raspberry PI3 
and Odroid XU4 embedded machines. 

# How to install qhyccd SDK driver:

1. There are two targz files, one for Intel processors, the second one for ARM V8 machines.
2. Copy an appropriate file to the place where you want to untar it.
3. Untar the targz file using: tar xzvf file_name.tar.gz.
4. Go to its install_scripts directory and run script: sudo ./linux_install_qhyccd_sdk_driver.sh. 
This command will install all the necessary files on your machine to run QHYCCD SDK driver.

# How to compile and run SingleFrameMode testing application:
1. The CMake version 2.6 or above should be installed on your machine.
2. Go to build subdirectory inside untared directory, for example:
soldan@nuc7i5:/data/qhy_tests/qhyccdsdk-1.0.6-Linux-Debian-x86_64$ ls
build  cmake_modules  doc  firmware  fx3load  include  install_scripts  lib  testapp  udev
soldan@nuc7i5:/data/qhy_tests/qhyccdsdk-1.0.6-Linux-Debian-x86_64$ cd build
remove all cmake files
3. soldan@nuc7i5:/data/qhy_tests/qhyccdsdk-1.0.6-Linux-Debian-x86_64/build$ rm -rf *
run cmake
4. soldan@nuc7i5:/data/qhy_tests/qhyccdsdk-1.0.6-Linux-Debian-x86_64/build$ cmake ../testapp/SingleFrameMode/
-- The C compiler identification is GNU 5.4.0
-- The CXX compiler identification is GNU 5.4.0
-- Check for working C compiler: /usr/bin/cc
-- Check for working C compiler: /usr/bin/cc -- works
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Detecting C compile features
-- Detecting C compile features - done
-- Check for working CXX compiler: /usr/bin/c++
-- Check for working CXX compiler: /usr/bin/c++ -- works
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Detecting CXX compile features
-- Detecting CXX compile features - done
PROJECT_SOURCE_DIR: /data/qhy_tests/qhyccdsdk-1.0.6-Linux-Debian-x86_64/testapp/SingleFrameMode
-- Found libusb-1.0:
--   Includes: /usr/local/include/libusb-1.0
--   Libraries: /usr/local/lib/libusb-1.0.so
-- Performing Test ERROR_NAME_COMPILE
-- Performing Test ERROR_NAME_COMPILE - Success
-- Configuring done
-- Generating done
-- Build files have been written to: /data/qhy_tests/qhyccdsdk-1.0.6-Linux-Debian-x86_64/build
run make
5. soldan@nuc7i5:/data/qhy_tests/qhyccdsdk-1.0.6-Linux-Debian-x86_64/build$ make
Scanning dependencies of target SingleFrameMode
[ 50%] Building CXX object CMakeFiles/SingleFrameMode.dir/SingleFrameMode.cpp.o
[100%] Linking CXX executable SingleFrameMode
[100%] Built target SingleFrameMode

connect your camera to USB port and run testing application
6. soldan@nuc7i5:/data/qhy_tests/qhyccdsdk-1.0.6-Linux-Debian-x86_64/build$ ./SingleFrameMode
SingleFrameMode, Version: 1.00
2017-12-15 17:03:59.370 LOG_ALARM -----------------  log4z thread started!   ---------------------------- 
2017-12-15 17:03:59.370 LOG_ALARM logger id=0 key=Main name=SingleFrameMode path=/tmp/ level=1 display=1   
SDK resources initialized.
Number of QHYCCD cameras found: 1 
Application connected to the following camera from the list: Index: 1,  cameraID = QHY163M-189b984ba3fe674f9
Open QHYCCD success.
SetQHYCCDStreamMode set to: 0, success.
InitQHYCCD success.
GetQHYCCDOverScanArea:
Overscan Area startX x startY : 0 x 0
Overscan Area sizeX  x sizeY  : 0 x 0
GetQHYCCDEffectiveArea:
Effective Area startX x startY: 0 x 0
Effective Area sizeX  x sizeY : 0 x 0
GetQHYCCDChipInfo:
Effective Area startX x startY: 0 x 0
Chip  size width x height     : 17.693 x 13.383 [mm]
Pixel size width x height     : 3.800 x 3.800 [um]
Image size width x height     : 4656 x 3522
This is a mono camera.
SetQHYCCDParam CONTROL_USBTRAFFIC set to: 10, success.
SetQHYCCDParam CONTROL_GAIN set to: 10, success
SetQHYCCDParam CONTROL_GAIN set to: 140, success.
SetQHYCCDParam CONTROL_EXPOSURE set to: 20000, success.
SetQHYCCDResolution roiStartX x roiStartY: 0 x 0
SetQHYCCDResolution roiSizeX  x roiSizeY : 4656 x 3522
SetQHYCCDBinMode set to: binX: 1, binY: 1, success.
SetQHYCCDParam CONTROL_GAIN set to: 10, success.
ExpQHYCCDSingleFrame(pCamHandle) - start...
ExpQHYCCDSingleFrame(pCamHandle) - end...
ExpQHYCCDSingleFrame success.
Allocated memory for frame: 32796864 [uchar].
GetQHYCCDSingleFrame: 4656 x 3522, bpp: 16, channels: 1, success.
CancelQHYCCDExposingAndReadout success.
Close QHYCCD success.
SDK resources released.
