# **MariaDB**


### **Installation on Ubuntu**

**Follow the guide to install MySQL :**   [**Install MariaDB**](https://mariadb.com/kb/en/building-mariadb-on-ubuntu//)

 1. Update package lists:

    Before installing any new packages, it's always a good idea to update the package lists for upgrades and new package installations. You can do this by running the following command in the terminal:

        > sudo apt-get update 

 2. Install software-properties-common:

    This package provides the add-apt-repository command, which allows you to add Personal Package Archives (PPAs) to your system.

        > sudo apt-get install software-properties-common

 3. Add a PPA:

    To add a PPA to your system, use the add-apt-repository command. For example, to add the official MariaDB PPA, run the following command in the terminal:

        > sudo add-apt-repository ppa:mariadb/mysql

    You will be prompted to enter your password. After entering the password, the PPA will be added to your system.

 4. Install packages:

    Now you can install packages from the PPA using the apt command, for example:

        > sudo apt-get update

        > sudo apt install mariadb-server

 5. Secure MariaDB:

    After installing MariaDB, you should run the MariaDB security script to improve the security of your installation. You can do this by running the following command in the terminal:

        > sudo mysql_secure_installation

    This script will prompt you to set the root password, remove anonymous users, disallow root login remotely, and remove the test database.

 6. MySQL database development files:
  
        > apt-get install mariadb-client-10.3

    This package provides the MariaDB client, which allows you to connect to a MariaDB server and execute SQL commands.

 7. Start and enable MariaDB:

    To start the MariaDB server and ensure that it starts automatically when the system boots, run the following commands in the terminal:

        > sudo systemctl start mariadb

        > sudo systemctl enable mariadb

 8. Access MariaDB:

    To access MariaDB, run the following command in the terminal:

        sudo mysql -u root -p

    You will be prompted to enter the password for the MariaDB root user.

 9. Create a new database and user:

    To create a new database and user, run the following commands in the MariaDB prompt:

        > CREATE DATABASE mydatabase;
        > CREATE USER 'myuser'@'localhost' IDENTIFIED BY 'mypassword';
        > GRANT ALL PRIVILEGES ON mydatabase.* TO 'myuser'@'localhost';
        > FLUSH PRIVILEGES;

    Replace mydatabase with the name of your database, myuser with the name of your user, and mypassword with the password for your user.

10. Change password :

    To change the password for a user in MariaDB, use the ALTER USER command in the MariaDB prompt. For example, the following command changes the password for the user myuser to newpassword:

        > ALTER USER 'myuser'@'localhost' IDENTIFIED BY 'newpassword';

    Replace myuser with the name of the user whose password you want to change, and newpassword with the new password that you want to set for the user. After changing the password, make sure to run the following command in the MariaDB prompt to flush the privileges:

        > FLUSH PRIVILEGES;

10. Exit MariaDB:
    
    To exit the MariaDB prompt, run the following command:

        > EXIT;

&nbsp;

### **Password Change** 

 1. Access MariaDB:
    
    To access MariaDB, run the following command in the terminal:

        > sudo mysql -u root -p

    You will be prompted to enter the password for the MariaDB root user.
          
 2. Change password of user:

    To change the password for a user in MariaDB, use the ALTER USER command in the MariaDB prompt. For example, the following command changes the password for the user myuser to newpassword:    

        > ALTER USER 'myuser'@'localhost' IDENTIFIED BY 'newpassword';

    OR

        > GRANT ALL PRIVILEGES ON mysql.* TO 'myuser'@'localhost';

    OR 

        > GRANT ALL PRIVILEGES ON *.* TO 'myuser'@'localhost' IDENTIFIED BY 'newpassword';

    Replace myuser with the name of the user whose password you want to change, and newpassword with the new password that you want to set for the user.

 3. Flush privileges:

    After changing the password, make sure to run the following command in the MariaDB prompt to flush the privileges:
    
        > FLUSH PRIVILEGES;

 4. Exit MariaDB:

    To exit the MariaDB prompt, run the following command:

        > EXIT;

    That's it! The password for the user has been changed in MariaDB.

&nbsp;

   **References:** 
   
 * [**mariadb.com**](https://mariadb.com/kb/en/building-mariadb-on-ubuntu//)

 * [**packages.ubuntu.com**](https://packages.ubuntu.com/search?keywords=mariadb-server)
