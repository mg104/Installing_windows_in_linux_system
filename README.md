# Making bootable Windows USB in Ubuntu

Steps are as follows:

1. Insert USB.

2. Format the USB:
   - Open "disks" app in Ubuntu.
   - Format the USB
   - Choose to overwrite the USB
   - Click on the "+" (Partition) sign and choose the name of the USB, say "Win10USB". Also choose "NTFS" option and not FAT32 option while doing this, because FAT32 limits the size of USB available to 4GB to write files on it and it could lead to files being truncated and errors while installing windows (specifically: install.wim file which is 4.6 GB in size and therefore might get truncated.)

3. Install Unetbootin on ubuntu by running the following commands:
   - sudo add-apt-repository ppa:gezakovacs/ppa
   - sudo apt-get update
   - sudo apt-get install unetbootin

4. Find out the mount point of the USB by running "df -h" in terminal. It should show something like following (if the name of the USB kept by you in above step, is "Win10USB"):
   - /dev/sdc1        15G   65M   15G   1% /media/madhur/Win10USB

5. Run the following commands in terminal:
   - sudo unetbootin installtype=USB targetdrive=/dev/sdc1

6. Unetbootin GUI will open automatically and then proceed with clicking on "Disk Image" option, and choose the ISO file location.

7. Proceed as usual.
