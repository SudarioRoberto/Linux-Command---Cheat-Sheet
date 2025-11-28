# Linux-Command---Cheat-Sheet

Commands for Linux

### 1-HARDWARE INFORMATION

 Display messages in kernel ring buffer
```
dmesg
```

Display CPU information

``` cat /proc/cpuinfo ```

Display memory information
``cat /proc/meminfo``

### Display free and used memory ( -h for human readable, -m for MB, -g for GB.)
free -h

### Display PCI devices
lspci -tv

### Display USB devices
lsusb -tv

### Display DMI/SMBIOS (hardware info) from the BIOS
dmidecode

### Show info about disk sda
hdparm -i /dev/sda

### Perform a read speed test on disk sda
hdparm -tT /dev/sda

### Test for unreadable blocks on disk sda
badblocks -s /dev/sda


## 2- FILE AND DIRECTORY COMMANDS

### List all files in a long listing (detailed) format
ls -al

### Display the present working directory
pwd

### Create a directory
mkdir directory

### Remove (delete) file
rm file

### Remove the directory and its contents recursively
rm -r directory

### Force removal of file without prompting for confirmation
rm -f file

### Forcefully remove directory recursively
rm -rf directory

### Copy file1 to file2
cp file1 file2

### Copy source_directory recursively to destination. If destination exists, copy source_directory into destination, otherwise create destination with the contents of source_directory.
cp -r source_directory destination

### Rename or move file1 to file2. If file2 is an existing directory, move file1 into directory file2
mv file1 file2

### Create symbolic link to linkname
ln -s /path/to/file linkname

### Create an empty file or update the access and modification times of file.
touch file

### View the contents of file
cat file

### Browse through a text file
less file

### Display the first 10 lines of file
head file

### Display the last 10 lines of file
tail file



## 3- Disk Usage 

### Show free and used space on mounted filesystems
df -h

### Show free and used inodes on mounted filesystems
df -i

### Display disks partitions sizes and types
fdisk -l

### Display disk usage for all files and directories in human readable format
du -ah

### Display total disk usage off the current directory
du -sh

### Display the last 10 lines of file and "follow" the file as it grows.
tail -f file


