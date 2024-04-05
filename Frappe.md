# **Frappe Framework**


### **Installation :**


**Follow the guide to install Frappe :**   [**Frappe-Framework**](https://frappeframework.com/docs/user/en/installation#debian-ubuntu)


 1. **Create a new user:**

    Create new user as a security measure to prevent root user access. New user will be assigned admin permissions and will be used as the main Frappe Bench user. [**New User**](https://github.com/SamSpace2497/Docs/blob/main/UbuntuSetup.md)

        > sudo adduser [newuser]

        > usermod -aG sudo newuser
        
        > su [newuser]

        > sudo mkdir /home/newuser

        > cd  /home/newuser

&nbsp;

### Prerequisites :   [**frappeframework.docs**](https://frappeframework.com/docs/user/en/prerequisites)

 2. **Update package lists:**

    Before installing any new packages, it's always a good idea to update the package lists for upgrades and new package installations. You can do this by running the following command in the terminal:

        > apt list --installed

        > sudo apt-get update -y
        
        > sudo apt-get upgrade -y
        

 3. **Install git and redis:**

        > sudo apt install git redis-server python3-pip


 4. **Install virtualenv for Python 3:**
    
    Virtualenv is a tool that allows you to create isolated Python environments. This is useful when you want to install and manage packages for a specific project without affecting other projects. To install virtualenv for Python 3, run the following command in the terminal:

        > sudo apt-get install python3-virtualenv

    *Set up the virtual environment for frappe:*

    To create a new virtual environment, navigate to the directory where you want to create the environment and run the following command, replacing myenv with the name of your virtual environment:

        > python3 -m venv myenv

    *Activate the virtual environment:*
    
    To activate the virtual environment, navigate to the directory where you created the environment and run the following command:

        > source myenv/bin/activate

 
 5. **Install & Configure MariaDB:**

    Follow instructions from [**MariaDB**](https://github.com/SamSpace2497/Docs/blob/main/MariaDB.md)

        > sudo apt-get install software-properties-common
        
        > sudo apt install mariadb-server mariadb-client
    
    *MariaDB configuration :*

    To open the MariaDB configuration file for editing, run the following command in the terminal:

        > sudo nano /etc/mysql/my.cnf

    This will open the MariaDB configuration file in the nano text editor. Add the following configuration to the end of the file:

        [mysqld]

        character-set-client-handshake = FALSE
        
        character-set-server = utf8mb4
        
        collation-server = utf8mb4_unicode_ci

        [mysql]

        default-character-set = utf8mb4

    After adding the configuration, save the changes and close the text editor by pressing Ctrl+X, then Y, then Enter. After editing the MariaDB configuration file, you need to restart the MariaDB server to apply the changes. You can do this by running the following command in the terminal:

        > sudo systemctl restart mariadb

    This will restart the MariaDB server and apply the new configuration.


 6. **Install Node:**

    Snap is a package manager for Linux that allows you to install and manage applications and packages. To install Snap on Ubuntu, run the following command in the terminal:

        > sudo apt install snapd

    Once Snap is installed, you can use it to install Node.js. To install Node.js, run the following command in the terminal:

        > sudo snap install node --classic

    This command installs the latest version of Node.js using the --classic flag, which allows the application to have full access to the system. 
    
  * *Install npm:*
    
    npm (Node Package Manager) is a package manager for Node.js that allows you to install and manage Node.js packages. To install npm, run the following command in the terminal:

        > sudo apt install npm


 7. **Install yarn:**

    To install Yarn, which is a package manager for Node.js, run the following command in the terminal:

        > sudo npm install -g yarn


 8. **Install wkhtmltopdf:**

        > sudo apt-get install xvfb libfontconfig

        > sudo apt-get install libmysqlclient-dev

    To download wkhtmltopdf, visit the [**official website**](https://wkhtmltopdf.org/downloads.html) and choose the version that matches your system. After downloading the installer, navigate to the directory where you downloaded the file and run the following command in the terminal:

        > sudo dpkg -i [downloaded file].deb 


 9. **Install Nginx & Supervisor:**

        > sudo apt -y install nginx supervisor



10. **Install Bench CLI:**

    Install Bench CLI using pip, by running the following command in the terminal:

        > pip install bench

    if  you get an error, open pip configuration file and make following changes:

        > sudo nano /etc/pip.conf

    *modify:*

        [global]
        break-system-package = true

    After succesfully editing, try installing bench again.


11. **Use Bench CLI:**

    To use Bench CLI, you can run the following command in the terminal:

        > cd ~
        
        > bench init --frappe-branch version-15 frappe-bench

    This will create a new Bench directory called frappe-bench. This will be the main directory from where we will be running all the commands.
    
    The full path of this directory will be: /home/[user]/frappe-bench/

    After the frappe-bench folder is created, change your directory to it and run this command

        > cd frappe-bench

        > bench start

    Change user directory permissions:

    This will allow execution permission to the home directory of the user we created in step 1

        > chmod -R o+rx /home/[newuser]/

    Congratulations, you have installed bench on to your system. Now you are ready to deploy any app or build with Frappe Framework.

12. **Create a New Site:**

    We will use this as the default site where ERPNext and other apps will be installed.

        > bench new-site site.localhost

13. **Install ERPNext and other Apps:**

    Download the necessary apps for the server

    Download the payments apps . This app is required during ERPNext installation

        > bench get-app payments

    Download & Install the main ERPNext app :

        > bench get-app --branch version-15 erpnext

        > bench --site site.localhost install-app erpnext

14. SETUP PRODUCTION SERVER:

    Enable scheduler service:

        > bench --site site.localhost enable-scheduler

    Disable maintenance mode:

        > bench --site site.localhost set-maintenance-mode off

    Setup production config:

        > sudo bench setup production [user]

    Setup NGINX web server:

        > bench setup nginx

    Final server setup:

        > sudo supervisorctl restart all

        > sudo bench setup production [user] 

    When prompted to save new/existing config files, hit “Y”

    You can now go to your server [IP-address]:80 and you will have a fresh new installation of ERPNext ready to be configured!

15. Test your Server:

    Open a browser and go to `http://your_server_ip` or `http://your_domain`. You should see the login screen of ERPNext. Use the credentials
   
    Open a browser and go to http://site.localhost (replace "site" with whatever you used in step 14) 

&nbsp;

###   **References:** 

 *  [**installation#debian-ubuntu**](https://frappeframework.com/docs/user/en/installation#debian-ubuntu)

 *  [**frappeframework.prerequisites**](https://frappeframework.com/docs/user/en/prerequisites)

 *  [**install_applications#bench-cli**](http://frappeframework.com/docs/user/en/install_applications#bench-cli)    

 *  [**New User**](https://github.com/SamSpace2497/Docs/blob/main/UbuntuSetup.md)

 *  [**discuss.frappe.io**](https://discuss.frappe.io/t/guide-how-to-install-erpnext-v14-on-linux-ubuntu-step-by-step-instructions/92960)

 *  [**erpnext.org**](https://erpnext.org/docs/user/manual/en/introduction/installation)

 *  [**MariaDB**](https://github.com/SamSpace2497/Docs/blob/main/MariaDB.md)

 *  [**wkhtmltopdf.org**](https://wkhtmltopdf.org/downloads.html)

 *  [**Guide-for-Developers**](https://github.com/frappe/frappe/wiki/Guide-for-Developers)

