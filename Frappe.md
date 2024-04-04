# **Frappe Framework**


### **Installation on Ubuntu**

**Follow the guide to install Frappe :**   [**`Frappe-Framework`**](https://frappeframework.com/docs/user/en/installation#debian-ubuntu)


 1. Update package lists:

    Before installing any new packages, it's always a good idea to update the package lists for upgrades and new package installations. You can do this by running the following command in the terminal:

        `> sudo apt-get update -y`
        
        `> sudo apt-get upgrade -y`

 2. Create a new user:

    Create new user as a security measure to prevent root user access. New user will be assigned admin permissions and will be used as the main Frappe Bench user. [**`New User`**](https://github.com/SamSpace2497/Docs/blob/main/UbuntuSetup.md)

        `> sudo adduser [newuser]`

        `> usermod -aG sudo newuser`
        
        `> su [newuser]`

        `> sudo mkdir /home/newuser`

        `> cd  /home/newuser`


 ### Prerequisites :  [frappeframework.docs](https://frappeframework.com/docs/user/en/prerequisites)

 3. Install git and redis:

        `> sudo apt install git redis-server python3-pip`

 4. 

    `> git clone https://github.com/frappe/bench ~/bench`
    
    `> cd ~/bench`

 5. Set up the virtual environment for frappe:

python3