# Installing mysql on Raspberry pi

* sudo apt install mariadb-server php-mysql -y

* sudo mysql_secure_installation

* sudo mysql --user=root --password
  * create user admin@localhost identified by 'your_password';
  * grant all privileges on *.* to admin@localhost;
  * FLUSH PRIVILEGES;
  * exit;

* **Setting up TCP connection**
  * mysqld --help --verbose  
    *executing this will give you default paths where configuration is saved. Look for .cnf file*  
    *usual places are /etc/my.cnf /etc/mysql/my.cnf ~/.my.cnf*  
    *look for skip-networking and bind-address*  
    *skip-network will turn off TCP and bind-address pointing to loopback will make clients unable to connect from outside localhost*
    
    * sudo nano /etc/mysql/mariadb.conf.d/50-server.cnf    
    *comment skip-network and bind-address lines*  
    
    * Restart the mariadb  
    *sudo systemctl restart mariadb*
    
    * Check the updates  
    *mysqld --print-defaults  
    This will print the changes*
    
