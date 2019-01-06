# Laravel Deployment On Ubuntu Server
### Before setting everything up there are few packages that you will need, which actually are available in Ubuntu Repositories.

## Steps
1.Install either Nginx Web Server or Apache.

```
sudo apt update
sudo apt install nginx
```
#### If you have the firewall running, it is important to allow connections to Nginx so enable it by typing

```
sudo ufw allow 'Nginx HTTP'
```
#### After that you can verify the changes by running 

```
sudo ufw status'
```
#### After installing Nginx successfuly test it on your browser by typing 
```
http://ip_address
```
on ip_address provide your ip address of the server. And yow will see welcome to Nginx Message.

2.Install Database (Choice will be Mysql for my case scenario). To install it type 
```
sudo apt install mysql-server

```
#### The script will ask you if you want to configure the VALIDATE PASSWORD PLUGIN. Answer YES
```
VALIDATE PASSWORD PLUGIN can be used to test passwords
and improve security. It checks the strength of password
and allows the users to set only those passwords which are
secure enough. Would you like to setup VALIDATE PASSWORD plugin?

Press y|Y for Yes, any other key for No:

```
```
There are three levels of password validation policy:

LOW    Length >= 8
MEDIUM Length >= 8, numeric, mixed case, and special characters
STRONG Length >= 8, numeric, mixed case, special characters and dictionary                  file

Please enter 0 = LOW, 1 = MEDIUM and 2 = STRONG: 1

```
#### Then confirm root password
```
Please set the password for root here.

New password: 

Re-enter new password: 

```
#### Test it by typing 
```
sudo mysql

```
3. Installing PHP and Configuring Nginx to use the PHP Processor
#### Let me remind you that make sure you installed Nginx successfully and mysql is running without any challenge. So since Nginx doesnot contain native PHP processing like other web server you need to install php-fpm (This is very important which stands for fastCGI process manager)
##### Add Ubuntu universe repository before installing php fpm by typing
```
sudo add-apt-repository universe

```
#### Then after install php-fpm and php mysql
```
sudo apt install php-fpm php-mysql

```