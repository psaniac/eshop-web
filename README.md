# eshop-web
An original eshop. Written in PHP. Uses an SQL database to store information. Written with security practices in mind.
## Features
- Products page
- Product detail page
- Shopping cart
- Orders - user can order products, admin can view and fulfill orders
- User accounts
- Sending emails on order creation
- Login with username/password or login with Google
- Administator accounts

## Setup
You will need a functioning webserver that supports PHP and an SQL server. They do not need to be on the same machine. You will also need an SMTP server if you want the email functionality to work.
1. Copy the eshop folder to the root of your webserver
2. Login to your SQL server
3. Create an empty database
4. Import one of the provided SQL files into the newly created databse for the eshop. The 'example' file has some test data to get you started, the 'empty' file has just the tables.
5. Edit eshop/assets/config/db-access.php
```
const DB_HOST = 'REDACTED'; -> SQL hostname
const DB_DATABASE = 'REDACTED'; -> database name
const DB_USERNAME = 'REDACTED'; -> login username
const DB_PASSWORD = 'REDACTED'; -> login password
```
7. Edit eshop/assets/config/smtp-config.php
```
const SMTP_Host = 'smtp.gmail.com'; -> SMTP server hostname
const SMTP_Username = 'REDACTED'; -> SMTP server username
const SMTP_Password = 'REDACTED'; -> SMTP server password
const SMTP_Port = '465'; -> SMTP port (default 465)
const SMTP_From = 'REDACTED'; -> The email address you are sending from
```
8. If you want Google login to work, edit the eshop/assets/config/google.php file. You will also need a Google account with Google Cloud Platform setup.
```
# Add your client ID and Secret
$client_id = "REDACTED";
$client_secret = "REDACTED";
# change this
$redirect_uri = 'http://localhost/account/login.php'
```
8. Open your web browser and connect to your webserver. You should see the webapp show up.
9. You will need to have an admin account. An admin account is an account with 10 or more in the 'privilege' column in the database. Easiest way to create is to create a regular account and edit it to be an admin account.
10. If you wish to customize your store, consider modifying these first:
- The main page at eshop/index.php
- Products can be added/removed in the database
- CSS style sheet at eshop/assets/css/style.css

Note: This project was created during a coding marathon in 4 days. 
