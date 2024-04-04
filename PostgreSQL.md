# **PostgreSQL**

### **Installation on Ubuntu**

**Follow the guide to install PostgreSQL :**   [**Install PostgreSQL**](https://www.postgresql.org/download/linux/ubuntu/)

 1. Update package lists:

    Before installing any new packages, it's always a good idea to update the package lists for upgrades and new package installations. You can do this by running the following command in the terminal:

        > sudo apt-get update

 2. Install Postgres:

    To install Postgres, run the following command in the terminal:

        > sudo apt-get install postgresql-12

    This will install the latest stable version of Postgres.

 3. Start and enable Postgres:
    
    To start the Postgres server and ensure that it starts automatically when the system boots, run the following commands in the terminal:

        > sudo systemctl start postgresql

        > sudo systemctl enable postgresql

 4. Access Postgres:

    To access Postgres, run the following command in the terminal:
 
        > sudo -u postgres psql

    You will be prompted to enter the password for the Postgres user.

 5. Create a new database and user:
    
    To create a new database and user, run the following commands in the Postgres prompt:

        > CREATE DATABASE mydatabase;
        > CREATE USER myuser WITH PASSWORD 'mypassword';
        > GRANT ALL PRIVILEGES ON mydatabase.* TO 'myuser';
    
    Replace mydatabase with the name of your database, myuser with the name of your user, and mypassword with the password for your user.

 6. Exit Postgres:
    
    To exit the Postgres prompt, run the following command:

        > \q

 7. Install Postgres client:

    To install the Postgres client, run the following command in the terminal:

        > sudo apt-get install postgresql-client

&nbsp;

### **References:** 
   
 * [**ubuntu.com**](https://ubuntu.com/server/docs/databases-postgresql)

 * [**postgresql.org**](https://www.postgresql.org/download/linux/ubuntu/)

