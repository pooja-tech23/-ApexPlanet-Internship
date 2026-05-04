1. File System Navigation
 pwd (Print Working Directory)
•	Shows current directory path 
pwd

 ls (List Files)
•	Displays files and folders 
ls        # basic
ls -l     # detailed list
ls -a     # hidden files

 cd (Change Directory)
•	Moves between directories 
cd folder_name     # go inside folder
cd ..              # move back
cd ~               # home directory
cd /               # root directory

2. File & Directory Permissions
 Permission Types
•	r → read 
•	w → write 
•	x → execute 
Example:
-rwxr-xr--

chmod (Change Permissions)
chmod 755 file.txt
 Meaning:
•	Owner → rwx (7) 
•	Group → r-x (5) 
•	Others → r-x (5) 

 chown (Change Ownership)
chown user file.txt
chown user:group file.txt 

3. Package Management
 apt (Advanced Package Tool)
Used in Debian/Kali/Ubuntu
sudo apt update        # update package list
sudo apt upgrade       # upgrade packages
sudo apt install nmap  # install package
sudo apt remove nmap   # remove package

 dpkg (Low-level package tool)
sudo dpkg -i file.deb     # install package
sudo dpkg -r package_name # remove package


4. Networking Commands
 ifconfig
•	Shows network configuration 
ifconfig

 ping
•	Checks connectivity 
ping google.com

 netstat
•	Shows network connections 
netstat -tuln

traceroute
•	Shows path packets take 
traceroute google.com
