# Making bootable Windows USB in Ubuntu

Steps are as follows:

1. Insert USB.

2. Format the USB:
   - Open "disks" app in Ubuntu.
   - Format the USB
   - Choose to overwrite the USB
   - Create a new Partition on the USB by clikcing on the "+" sign and choose the name of the USB, say "Win10USB". Also choose "NTFS" formatting option and      not FAT32 option while formatting, because FAT32 limits the size of USB available to 4GB to write files on it and it could lead to files being  
     truncated and errors while installing windows (specifically: install.wim file which is 4.6 GB in size and therefore might get truncated.)

3. Install Unetbootin on ubuntu by running the following commands:
   - sudo add-apt-repository ppa:gezakovacs/ppa
   - sudo apt-get update
   - sudo apt-get install unetbootin

4. Open Unetbootin and click on the ISO file and proceed as per instructions

5. Boot into UEFI (by pressing F11 in MSI BIOS 5, when the system restarts) and install windows.
