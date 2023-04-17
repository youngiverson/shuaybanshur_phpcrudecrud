Section #1 that describes, in brief, the purpose of the PHP Crude CRUD Application.  What does it allow the user to do?
The PHP Crude Crud Applications purpose is to give us a better understanding of how dynamic data driven web applications work. It creates a LAMP server on the local machine that lets the user add, update, delete and search for employees on the MySQL Database.

Section #2 that describes at a high level what the general steps are to create and an entirely new application architecture and stack from the "ground up."  Start with the provisioning of the Virtual Machine.  End with the deploying the PHP Crude CRUD app.  Just a few sentences.  Again this is just an overview, so the admin knows what's involved at the high-level.

Make sure to install VMware Fusion and create a VM using the default settings. 
Then Install Apache2, PHP and MySQL. You can now create and store the files in the /var/www/html directory. You can then deploy the web app by using the IP associated with the server in your browser

Section #3 - suggested Virtual Machine configuration:  disk, cpu, ram.
Disk: 20 GB, CPU: 1, RAM: 2048

Section #4 - Step by step instructions on how to create a Virtualbox Virtual Machine.

1. Download and install VMware Fusion. 
2. Once you get to the home screen press the + button and press new. 
3. Click Create a custom VM then press Linux and then Ubuntu 64 Bit. Make sure you create a new virtual disk and then you'll have a VM made 


Section #5 - Step by step instructions on how to install the Ubuntu 20.04 Operating System.
1. Search up Ubuntu 20.04 and download the desktop image 
2. Open your VM and click the CD image > Choose Disc Image > The ubuntu desktop image
3. Click the CD image again and press connect CD Then restart your vm

Section #6 - Step by step instructions on how to install Apache 2 and PHP
1. Go to your terminal and sign into your VM
2. Run the following commands
3. sudo apt update
4. sudo apt upgrade
5. sudo apt install apache2
6. sudo apt install php libapache2-mod-php php-cli php-mysql php-mgsql


Section #7 - Step by step instructions on how to install MySQL

Run the following commands:
1. sudo apt update
2. sudo apt upgrade
3. sudo apt install mariadb-server
4. sudo systemctl status mariadb
5. mysql -V
6. sudo mysql_secure_installation


Section #8 - Configuration information regarding connection and credentials needed for PHP to connect to the database. 

The configuration information is stored in the credentials.php file which is in the /var/www/html/ directory. 

Section #9 - Step by step instructions on how to deploy the PHP Crude CRUD Application
1. Download the private key INET4031_Spring_2023.pem and put it in the .ssh directory
2. Zip file your php application using: 
tar -zcvf <your name>_phpcrudecrud.tar.gz phpcrudecrudapp/
3. scp -i .ssh INET4031_Spring_2023.pem <yourname>_phpcrudecrud.tar.gz ubuntu@18.119.121.213:.
 4. SSH into the server:
  ssh -i .ssh/INET4031_Spring_2023.pem ubuntu@18.119.121.213
 5.tar -xvf <yourname>_phpcrudecrud.tar.gz
  6. ubuntu@ip-172-31-3-146:~$ mv phpcrudecrudapp/ <your name>_phpcrudecrud
  7. sudo cp -R <yourname>_phpcrudecrudapp/ /var/www/html
you can now check to see if your php crude crud app works by typing
  http://18.119.121.213/_phpcrudecrudapp
Section #10 - Suggest system tests to run to make sure the Application is working.
You can try adding an employee to the database from the webpage and try to search for them to see if it works. 
  Another test you can run is deleting an employee and then checking to see if it was deleted


