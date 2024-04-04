# **Ubuntu Setup**


### **Installation**

**Follow the guide to install Ubuntu :**  [**`Install Ubuntu desktop`**](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)

 1. Download Ubuntu ISO :
     
    Goto [**`Ubuntu Website`**](https://ubuntu.com/download/desktop) & download Ubuntu image(ISO file).
  
 2. Create a Bootable USB :

    Install [**`balenaEtcher`**](https://etcher.balena.io/#download-etcher), select image, choose USB flash drive, and click **Flash!** to install your image.

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
  
    `> sudo apt-get update && sudo apt-get dist-upgrade`
  
    `> sudo apt-get install ubuntu-restricted-extras`

