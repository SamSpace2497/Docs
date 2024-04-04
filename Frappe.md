# **Frappe Framework**


### **Installation **

**Follow the guide to install Frappe :**   [**`Frappe-Framework`**](https://frappeframework.com/docs/user/en/installation#debian-ubuntu)

 1. Create a new user:

    Create new user as a security measure to prevent root user access. New user will be assigned admin permissions and will be used as the main Frappe Bench user. [**`New User`**](https://github.com/SamSpace2497/Docs/blob/main/UbuntuSetup.md)

        > sudo adduser [newuser]

        > usermod -aG sudo newuser
        
        > su [newuser]

        > sudo mkdir /home/newuser

        > cd  /home/newuser



 ### Prerequisites :  [frappeframework.docs](https://frappeframework.com/docs/user/en/prerequisites)

 2. Update package lists:

    Before installing any new packages, it's always a good idea to update the package lists for upgrades and new package installations. You can do this by running the following command in the terminal:

        > apt list --installed

        > sudo apt-get update -y
        
        > sudo apt-get upgrade -y

 3. Install git and redis:

        > sudo apt install git redis-server python3-pip

 4. Install virtualenv for Python 3:
    Virtualenv is a tool that allows you to create isolated Python environments. This is useful when you want to install and manage packages for a specific project without affecting other projects. To install virtualenv for Python 3, run the following command in the terminal:

        > sudo apt-get install python3-virtualenv

 5. Set up the virtual environment for frappe:

    To create a new virtual environment, navigate to the directory where you want to create the environment and run the following command, replacing myenv with the name of your virtual environment:

        > python3 -m venv myenv

 6. Activate the virtual environment:
    
    To activate the virtual environment, navigate to the directory where you created the environment and run the following command:

        > source myenv/bin/activate
 
 7. Install MariaDB:

    Follow instructions from [MariaDB](https://downloads)

    

    

 6. 


