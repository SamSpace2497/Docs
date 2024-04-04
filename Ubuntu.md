# **Ubuntu Setup**

### **Installation :**

   You can install Linux in several ways, depending on your preferences and technical expertise. Here are some common methods:

   * Dual Boot
   
   * Live CD/USB
   
   * Virtual Machine
   
   * Wubi
   
   * Network Install
   
   * Pre-Installed Systems

     This guide explains Ubuntu installation using USB flash drive. Follow the official guide to install Ubuntu : [**Install Ubuntu desktop**](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)

 1. Download Ubuntu ISO :
     
    Go to the [**Official Ubuntu Website**](https://ubuntu.com/download/desktop) and download the latest stable version of Ubuntu. You will  download a Ubuntu image(ISO file).
  
 2. Create a Bootable USB :

    Use a tool like [**balenaEtcher**](https://etcher.balena.io/#download-etcher) to create a bootable USB drive with the Ubuntu ISO file you downloaded. select downloaded ISO file, choose USB flash drive, and click **Flash!** to install your image.


 3. Backup : 

    Before you start the installation, it's a good idea to backup any important data on your computer. While it's unlikely that anything will go wrong, it's always better to be safe.


 4. Boot from USB: 

    Insert the USB flash drive into the laptop or PC you want to use to install Ubuntu and Restart your computer and boot from the USB drive. You may need to change the boot order in your BIOS settings to do this.It should recognise the installation media automatically. If not, try holding F12 during startup and selecting the USB device from the system-specific boot menu. 


 5. Start Ubuntu Installation: 

    Once you've booted from the USB drive, you'll see the Ubuntu installation menu. Select "Install Ubuntu" and press enter.


 6. Select Language and Keyboard Layout: 

    On the next screen, select your language and keyboard layout.

  
 7. Prepare Installation: 

    You'll be asked what kind of installation you want to perform. If you want to install Ubuntu alongside another operating system, select "Install Ubuntu alongside [other OS]". If you want to replace your existing operating system with Ubuntu, select "Erase disk and install Ubuntu". If you want to manually partition your disk, select "Something else".


 9. Allocate Drive Space: 

    If you choose to manually partition your disk, you'll be asked to allocate drive space for Ubuntu. This involves creating and sizing partitions for root, home, and swap.


10. Select Location: 

    On the next screen, select your location. This will be used to set your time zone.


11. Login Details: 

    You'll be asked to enter your name, computer's name, username, and password. Make sure to use a strong password.


12. Installation: 

    The installation will now begin. This may take a few minutes.


13. Restart: 

    Once the installation is complete, you'll be asked to restart your computer.

    
14. Remove USB: 
    
    Remove the USB drive when prompted, then press enter to restart your computer.


15. Login: 

    After your computer has restarted, you'll be taken to the login screen. Enter your username and password to log in.


16. Update and Install Software: 

    Once you've logged in, you should update your system and install any necessary software. You can do this by opening the terminal (Ctrl+Alt+T) and running the following commands:
  
        > sudo apt-get update && sudo apt-get dist-upgrade
  
        > sudo apt-get install ubuntu-restricted-extras

&nbsp;

### **New User**

   Create new users as a security measure to prevent root user access. New user will be assigned to selective permissions.

1. Add new user:
   
   Use the adduser command to add the new user, followed by the username. For example:
  

       > sudo adduser [newuser]

       > su [newuser] (to switch to the new user)


2. Create home directory:

   The adduser command creates the home directory for the new user and sets the correct permissions. If the home directory is not created, you can create it manually using the following command:

       > sudo mkdir /home/newuser

       > cd  /home/newuser

       > sudo chown newuser .


3. Set user password:

   To set the password for the new user, use the passwd command followed by the username. For example:

       > sudo passwd newuser

   You will be prompted to enter a password for the new user.


4. Grant sudo privileges:

   To grant sudo privileges to the new user, you need to add them to the sudo group. You can do this by editing the sudoers file using the visudo command. Add the following line to the file, replacing newuser with the name of the new user:

       > newuser ALL=(ALL:ALL) ALL

       > usermod -aG sudo newuser  


5. Confirm sudo privileges:

   To confirm that the new user has sudo privileges, log out of the system and log back in as the new user. Then, run the following command to test sudo:

       > sudo ls -la /root

   If the new user has sudo privileges, they will be able to run the command without any issues.

&nbsp;

   **References:** 
   
 * [**install-ubuntu-desktop#1-overview**](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)

 * [**balenaEtcher**](https://etcher.balena.io/#download-etcher)
