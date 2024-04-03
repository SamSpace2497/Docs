# **UBUNTU**


### **Installation**

**Follow the guide to install Ubuntu :**  [`Install Ubuntu desktop`](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)

  1. Download Ubuntu ISO : Goto [Ubuntu Website](https://ubuntu.com/download/desktop) & download ubuntu image(ISO file).
  
  2. Create a Bootable USB : Install **balenaEtcher** , Select downloaded ISO file, choose USB flash drive, and then click Flash! to install your image.

* Backup Important Data: 

  Before you start the installation, it's a good idea to backup any important data on your computer. While it's unlikely that anything will go wrong, it's always better to be safe.

* Boot from USB: 

  Insert the USB flash drive into the laptop or PC you want to use to install Ubuntu and Restart your computer and boot from the USB drive. You may need to change the boot order in your BIOS settings to do this.It should recognise the installation media automatically. If not, try holding F12 during startup and selecting the USB device from the system-specific boot menu. 

* Start Ubuntu Installation: 

  Once you've booted from the USB drive, you'll see the Ubuntu installation menu. Select "Install Ubuntu" and press enter.

* Select Language and Keyboard Layout: 

  On the next screen, select your language and keyboard layout.

* Prepare Installation: 

  You'll be asked what kind of installation you want to perform. If you want to install Ubuntu alongside another operating system, select "Install Ubuntu alongside [other OS]". If you want to replace your existing operating system with Ubuntu, select "Erase disk and install Ubuntu". If you want to manually partition your disk, select "Something else".

* Allocate Drive Space: 

  If you choose to manually partition your disk, you'll be asked to allocate drive space for Ubuntu. This involves creating and sizing partitions for root, home, and swap.

* Select Location: 

  On the next screen, select your location. This will be used to set your time zone.

* Login Details: 

  You'll be asked to enter your name, computer's name, username, and password. Make sure to use a strong password.

* Installation: 

  The installation will now begin. This may take a few      minutes.

* Restart: 

  Once the installation is complete, you'll be asked to restart  your computer.

* Remove USB: 

  Remove the USB drive when prompted, then press enter to  restart your computer.

* Login: 

  After your computer has restarted, you'll be taken to the login screen. Enter your username and password to log in.

* Update and Install Software: 

  Once you've logged in, you should update   your system and install any necessary software. You can do this by opening the terminal (Ctrl+Alt+T) and running the following commands:
  
  `> sudo apt-get update && sudo apt-get dist-upgrade`
  
  `> sudo apt-get install ubuntu-restricted-extras`
