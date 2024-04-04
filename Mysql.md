# **MySQL**


### **Installation on Ubuntu**

**Follow the guide to install MySQL :**   [**`Install MySQL`**](https://dev.mysql.com/doc/mysql-apt-repo-quick-guide/en/)

 1. Update package lists:

    Before installing any new packages, it's always a good idea to update the package lists for upgrades and new package installations. You can do this by running the following command in the terminal:

        > sudo apt-get update

 2. Install MySQL server:

    To install MySQL server, run the following command in the terminal:

        > sudo apt-get install mysql-server

    You will be prompted to enter a password for the MySQL root user. Make sure to choose a strong password and remember it.

 3. Run the MySQL security script:
    
    After installing MySQL server, you should run the MySQL security script to improve the security of your installation. You can do this by running the following command in the terminal:

        > sudo mysql_secure_installation

    You will be prompted to enter the current password for the MySQL root user. Then, you will be asked to set a new password for the MySQL root user, remove the anonymous user, disable remote root login, and remove the test database.

 4. Start and enable MySQL:

    To start the MySQL server, run the following command in the terminal:
 
        > sudo systemctl start mysql

    To ensure that the MySQL server starts automatically when the system boots, run the following command in the terminal:   

        > sudo systemctl enable mysql 

 5. Access MySQL:
    
    To access MySQL, run the following command in the terminal:

        > mysql -u root -p

    You will be prompted to enter the password for the MySQL root user.

 6. Create a new database and user:
    
    To create a new database and user, run the following commands in the MySQL prompt:

        > CREATE DATABASE mydatabase;
        > CREATE USER 'myuser' IDENTIFIED BY 'mypassword';
        > GRANT ALL PRIVILEGES ON mydatabase.* TO 'myuser';
        > FLUSH PRIVILEGES;
    
    Replace mydatabase with the name of your database, myuser with the name of your user, and mypassword with the password for your user.

 7. Exit MySQL:
    
    To exit the MySQL prompt, run the following command:

        `> EXIT;`

    That's it! You have successfully installed and set up MySQL on Ubuntu. You can now start using MySQL for your database needs.





### **Password Change** 

 1. Access MySQL:
    
    To access MySQL, run the following command in the terminal:

        > mysql -u root -p

    You will be prompted to enter the password for the MySQL root user.
          
 2. Change password:

    Once you are logged in to MySQL, you can change the password for a user by running the following command in the MySQL prompt:      

        > ALTER USER 'username' IDENTIFIED BY 'newpassword';

    OR

        > UPDATE USER SET PLUGIN = 'newpassword' WHERE USER = 'username'   

    Replace username with the name of the user whose password you want to change, and newpassword with the new password that you want to set for the user.

 3. Exit MySQL:

    Once you have changed the password, run the following command to exit the MySQL prompt:
    
        > EXIT;




### **Access as sudo user**
 -  To access mysql as a sudo user from the terminal, use the following command instead of "mysql":
     
        > sudo mysql -u username -p



 
### **Uninstall MySQL**

 1. Stop MySQL:
    
    First, you need to stop the MySQL server by running the following command in the terminal:

        > sudo systemctl stop mysql

 2. Uninstall MySQL:

        > sudo apt-get remove --purge mysql-server mysql-client mysql-common

    This command will remove the MySQL server and client packages and any configuration files associated with them.

 3. Remove MySQL data directory:
    
    If you want to remove the MySQL data directory, which contains the databases and other data, you can use the following command:

        > sudo rm -rf /var/lib/mysql

 4. Remove other MySQL packages:

    To remove any other MySQL packages that may have been installed, you can use the following command:

        > sudo apt-get autoremove

        > sudo apt-get autoclean

    This command will remove any packages that were installed as dependencies of MySQL but are no longer needed.

 5. Check for remaining MySQL packages:

    To check if there are any remaining MySQL packages on your system, you can use the following command:

        > dpkg -l | grep mysql

    If there are any remaining packages, you can remove them using the apt-get remove command.

    That's it! MySQL has now been uninstalled from your Ubuntu system.

