Deployment Procedure
====================
To view the functioning Chatbot, you must host the NodeJS application on a remote server and configure the SwiftChatbot application portal to connect with the NodeJS application.

Steps to deploy
------------------------

1. **Setup EC2 Instance:** To set up an EC2 instance (if not already done or if you wish to set up a new instance) in the ap-south-1 region with Ubuntu AMI, 16 GB storage, and t2.small compute power, follow this: `Ec2 Instance Setup Guide <ec2_instance.html>`_

.. note::
    Download the generated .pem file and store it securely on your local system. This file will be used for SSH access to the EC2 instance.

2. **SSH into Instance:** Use the following command to SSH into the instance with the provided .pem file:

``` ssh -i "<Your_PEM_file_name>" <Your_Host_IP_address_or_Domain_Name> ```

3. **To set up the necessary software components, follow these steps:**

- Update and upgrade the system packages:
```
sudo apt update
sudo apt upgrade
```

- Install Node.js, npm, Nginx, and PM2:
```
sudo apt install -y nodejs npm nginx
```

```
sudo npm install -g pm2
```

- (Optional) Install MySQL if you prefer setting up a local MySQL instance instead of using AWS RDS:
```
sudo apt install -y mysql-server
```

- Configure the MySQL root password:
```
sudo mysql -e "ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'mypassword';
```

.. note::
    If you are using AWS RDS, create a new user and grant all permissions. These credentials will be used when setting up the .env file later.

.. tip::
    If the root password does not change using the command above, follow the instructions provided `here <https://stackoverflow.com/questions/42421585/default-password-of-mysql-in-ubuntu-server-16-04>`_.


4. **Update .env file:**
To include the .env file in the cloned project root directory, you have two options:

1. **Option 1**: Create the .env file directly in the project root directory:
   
   - Navigate to the project root directory.
   - Execute the following command to create and open the .env file in the vi editor:

     ```
     vi .env
     ```

   - Press "i" to enter insert mode.
   - Paste the contents of the .env file (you can obtain it from your local .env file or ask your team leader for it).
   - Press "ESC" to exit insert mode.
   - Type ":wq" and press Enter to save and exit the vi editor.
   - You can verify the content of the .env file by running:

     ```
     cat .env
     ```

2. **Option 2**: Use SCP to copy the .env file from your local computer to the host computer:

   - Before proceeding, ensure that you are logged out from the host machine or open a different terminal window.
   - Use the following SCP command format:
   
     ```
     scp -i <PATH_TO_PRIVATE_KEY> <LOCAL_FILE_PATH> ec2-user@<EC2_PUBLIC_IP>:<REMOTE_PATH>
     ```
    
     Replace:

     - `<PATH_TO_PRIVATE_KEY>` with the path to your private key file.
     - `<LOCAL_FILE_PATH>` with the path to the .env file on your local computer.
     - `<EC2_PUBLIC_IP>` with the public IP address of your EC2 instance.
     - `<REMOTE_PATH>` with the path on the remote EC2 instance where you want to copy the .env file.

These options allow you to effectively include the .env file in your project directory, providing the necessary configurations for your application.