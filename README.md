# QHYCCD_Linux_New
This QHYCCD SDK repository contains targz files supporting Intel 64 bit Ubuntu Linux and ARM V8 processors. The Linux version was tested on Intel Core I7 processor. The ARM version was tested with Raspberry PI3 and Odroid XU4 embedded machines. 

How to use it:

1. There are two targz files, one for Intel processors, the second one for ARM V8 machines.
2. Copy an appropriate file to the place where you want to untar it.
3. Untar the targz file using: sudo tar xzvf file_name.tar.gz.
4. Go to its install_scripts directory and run script: sudo ./linux_install_qhyccd_sdk_driver.sh. This command will install all the necessary files on your machine to run QHYCCD SDK driver.
