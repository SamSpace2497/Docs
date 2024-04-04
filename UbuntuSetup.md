# **Ubuntu Setup**

&nbsp;

### **Installation :**

  You can install Linux in several ways, depending on your preferences and technical expertise. Here are some common methods:

   * Dual Boot
   
   * Live CD/USB
   
   * Virtual Machine
   
   * Wubi
   
   * Network Install
   
   * Pre-Installed Systems

     This guide explains Ubuntu installation using USB flash drive. Follow the official guide to install Ubuntu : [**Install Ubuntu desktop**](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)

     &nbsp;

 1. Download Ubuntu ISO :
     
    Goto [**Ubuntu Website**](https://ubuntu.com/download/desktop) & download Ubuntu image(ISO file). 

  
 2. Create a Bootable USB :

    Install [**balenaEtcher**](https://etcher.balena.io/#download-etcher), select image, choose USB flash drive, and click **Flash!** to install your image.


 3. Backup : 

    Before installation, backup important data from device for safety.


 4. Boot from USB: 

    Insert USB flash drive, install Ubuntu, restart and boot from USB drive. Hold F12 for system-specific boot menu. 


 5. Start Ubuntu Installation: 

    From Ubuntu installation menu, select "Install Ubuntu" and press enter.


 6. Select Language and Keyboard Layout: 

    On the next screen, select your language and keyboard layout.

  
 7. Prepare Installation: 

    Ubuntu alongside another operating system? "Install Ubuntu alongside [other OS]".

    Replace existing OS with Ubuntu? "Erase disk and install Ubuntu".

    For manual partition of disk, select "Something else".


 9. Allocate Drive Space: 

    Allocate drive space for Ubuntu (Involves creating and sizing partitions for root, home, and swap).


10. Select Location: 

    Select location to set time zone.


11. Login Details: 

    Enter name, device name, username, and password.


12. Installation: 

    Installation begins, may take few minutes.


13. Remove USB & Restart: 

    Once installation completes, remove USB & restart device.


14. Login: 

    After restart, login with username and password.


15. Update and Install Software: 

    Once logged in, update system and install necessary software by running following commands on terminal (Ctrl+Alt+T).
  
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

   References: 
   
 * [**install-ubuntu-desktop#1-overview**](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)

 * [**balenaEtcher**](https://etcher.balena.io/#download-etcher)





