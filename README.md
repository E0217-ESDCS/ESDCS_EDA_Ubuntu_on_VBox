
### 3️⃣ Option 3: Installing Ubuntu 22.04.5 in VirtualBox 

#### Step 1: Install VirtualBox
Download from: [VirtualBox Download](https://www.virtualbox.org/wiki/Downloads)

#### Step 2: Create VM (Click on New)
- Name: `Ubuntu-ESDCS`  (you can choose another name)
- RAM: **2 GB (min)**  
- CPU: **4 cores (min)**  
- Disk: **25 GB**
- Video Memory: **128 MB**

#### Step 3: Install Ubuntu
- Download ISO: [Ubuntu 22.04.5 LTS](https://releases.ubuntu.com/22.04.5/)
  Download Ubuntu desktop (not server). File name will be `ubuntu-22.04.5-desktop-amd64.iso`.
- Mount ISO in VM → Start VM → Install Ubuntu.  

#### Step 4: Update packages
Inside Ubuntu VM, run the following commands one by one. Enter your password when prompted.
```bash
sudo apt update
sudo apt upgrade
```

#### Step 5: Install EDA Tools
Inside Ubuntu VM:
```bash
sudo apt install -y iverilog yosys opensta gtkwave 
```

#### Step 6: Verify
```bash
iverilog -V
yosys -V
sta -help 
gtkwave -h
lsb_release  -a 
```

#### Step 7: Shared Clipboard
Enable shared clipboard bidirectionally
 `Devices > Shared Clipboard`  

#### Step 8: Guest Additions
To install guest additions go to 
 `Devices > Insert Guest Additions CD Image..`  

Then click on the CD disk visible in Ubuntu taskbar. A directory will open. Right-click inside the directory and select `Open in Terminal`. Then run 

```bash
./autorun.sh
```

#### Step 9: Shared Folder (For sharing files)
Enable shared folder  
 `Devices > Shared Folders`  
 Choose a Windows folder that you want to be shared with Ubuntu. Check Auto-mount and Make Permanent options.
 Then open terminal and enter the following command
 
 ```bash
sudo adduser $USER vboxsf
```

#### Step 10: Restart VM
Restart the VM to apply changes.
(Mandatory: Please refer to Annexure A for the required folders)  

---
