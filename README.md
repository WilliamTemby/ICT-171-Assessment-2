Student name: William Temby

Student ID: 35578349

Domain name: https://williamtemby171.com/

Video explainer: https://murdochuniversity-my.sharepoint.com/:v:/g/personal/35578349_student_murdoch_edu_au/EYY1uOOoaKNAt4svqqtdnK0BhN78-BI77gbxe6MtRMSWCQ?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=MZDmJS

(Note: this requires you to be signed into a Murdoch account in order to view)



**Server Setup Documentation**

1. Create an Amazon EC2 account if not already done.

   1a. Navigate to <https://signin.aws.amazon.com/signup?request_type=register>

   1b. Follow all on-site prompts to create your account. Note that your account will be required to have 2-factor authentication enabled.

2. In the top-right of the navigation bar, ensure that **Asia Pacific (Singapore)** is selected from the drop-down menu. 

![image](https://github.com/user-attachments/assets/04d805b9-08d2-457d-a545-edd2fbc8dae3)


3. Navigate EC2 dashboard, then select the orange **Launch instance** button.

![image](https://github.com/user-attachments/assets/a6d43633-3337-4ed0-b8b2-e105fbef3bc9)


4. In the **Applications and OS Images (Amazon Machine Image)** menu, select **Ubuntu** from the **Quick Start** tab. Leave the **Architecture** as **64-bit (x86).**

![image](https://github.com/user-attachments/assets/88e89a7a-b5ef-4e02-bc5e-506ad507fea1)


5. Create a new **Key pair.**

5a. On the **Key pair (login)** panel, select the **Create new key pair** link

![image](https://github.com/user-attachments/assets/a4375ac7-657a-4119-996d-ad5cf8a8dda1)


5b. In the **Create key pair** dialog box, enter a name you wish to use for the keys. Ensure that **RSA** is selected for the **Key pair type** and that the **Private key file format** is **.pem**.
    
![image](https://github.com/user-attachments/assets/8958281c-02e8-459e-aa95-407758b25f78)
    
    
5c. After selecting **Create new key pair,** a new .pem file will begin downloading. **IMMEDIATELY BACK THIS UP TO YOUR ONEDRIVE OR OTHER SECURE CLOUD STORAGE ACCOUNT**.
    
![image](https://github.com/user-attachments/assets/e50331e9-0ddc-4d0f-95ba-08b9d3d7579d)


6. Change instance IP to static

6a. Navigate to the dashboard and select "Elastic IPs"

![image](https://github.com/user-attachments/assets/b9782ad0-5376-4ba3-800a-08ed495f9d35)


6b. Right-click on the server you wish to allocate an elastic IP to, and select "Allocate Elastic IP address" in the context menu

![image](https://github.com/user-attachments/assets/beb1ffed-98f5-4b51-9ebf-71a8d968496a)


6c. Click the "Allocate" button in the menu - changing any settings is not required

![image](https://github.com/user-attachments/assets/23df8585-6a72-4cd8-87b7-15248f785b1f)


7. SSH into the server (Note, this documentation and explainer video makes use of MobaXterm, which offers a free version that will suffice for this)

7a. Return back to the server instances, and copy the Elastic IP address of the server you wish to SSH into

![image](https://github.com/user-attachments/assets/8659959a-8d56-4d7c-babb-c68b8279ed24)


7b. Launch MobaXterm, then select "Session" tile in the top left, then "SSH" on the dialog box in the same location, and finally "Advanced SSH settings"

![image](https://github.com/user-attachments/assets/ade61503-86b7-48b5-9405-af79b4b8daaf)


7c. Populate the dialogue boxes with the copied IP, username (This should just be ubuntu, if not, right-click your server instance in EC2, select "Connect to instance", then "SSH Client", and copy the name before the "@ec2" string)

![image](https://github.com/user-attachments/assets/c03eabd8-95ec-4f68-a9df-104e413b53a8)


8. Install Apache2 by running "sudo apt install apache2" into the command line. Ensure you select yes on any dialogs


![image](https://github.com/user-attachments/assets/e4cc5ab4-88b4-4be5-bb18-dfc287fbe791)


9. Test your server by navigating to http://\[Insert your elastic IP] in a web browser

![image](https://github.com/user-attachments/assets/7e190f96-e9ee-4d41-9a4f-b7cc139ebb18)


10. Install php and mySQL by running "sudo apt install php libapache2-mod-php php-mysql". Confirm yes on any dialoges

![image](https://github.com/user-attachments/assets/93bd4333-9463-4a16-9d60-48655a0fdd67)


11. Install mySQL server by running "sudo apt install mysql-server". Confirm yes on any dialoges

![image](https://github.com/user-attachments/assets/b702c581-edf1-42ba-b429-31127974f8a5)


12. Create mySQL account

12a. Run "sudo mysql -u root"

![image](https://github.com/user-attachments/assets/c9635cfc-4b86-49d8-a83d-99c14aee6229)


12b. Run "ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by '\[INSERT PASSWORD]';"

![image](https://github.com/user-attachments/assets/f78554d5-c9bf-4a5a-b864-35aada70fdb5)


12c. Run "CREATE USER '\[INSERT USERNAME]'@localhost IDENTIFIED BY '\[INSERT PASSWORD]';"

![image](https://github.com/user-attachments/assets/31c74188-12e4-4459-a900-5600d4d4cc48)


13. Create a database by running "CREATE DATABASE wp;"

![image](https://github.com/user-attachments/assets/13fe9d03-b39e-4433-9a50-21c5833b6fa0)


14. Grant privileges to the new user by running "GRANT ALL PRIVILEGES ON wp.* TO '\[INSERT USERNAME]'@localhost;"

![image](https://github.com/user-attachments/assets/0d078c5e-1345-4621-9e27-ddeaf01f68bc)


15. Press ctrl+D to exit mySQL, then create a temp folder by running "sudo mkdir temp"

![image](https://github.com/user-attachments/assets/ffbb3b5f-2832-46ec-b7d6-e20c1ad0441e)


16. cd into the temp folder by running "cd /home/ubuntu/temp/"

![image](https://github.com/user-attachments/assets/16473c9b-e896-42d8-a67f-b4ea4c811426)


17. Download Wordpress

17a. Navigate to wordpress.org in a web browser, and select the top-right "Get WordPress" button

![image](https://github.com/user-attachments/assets/572895b4-c063-4355-bcc6-bdc822ef9201)


17b. Select the "Releases" link on the "Get WordPress page

![image](https://github.com/user-attachments/assets/320ab80d-c18b-44f7-bc86-c0f0cfdec066)


17c. Right-click and select "Copy Link" on the "tar.gz" link for the latest release

![image](https://github.com/user-attachments/assets/4075b6de-473b-4538-aed9-91324af17c35)


17d. Run "sudo wget \[THE LINK YOU COPIED]"

![image](https://github.com/user-attachments/assets/8d6a4a12-c2e8-4e14-9164-cba2b18613f5)


17e. Run "sudo tar -xvf \[FILE YOU DOWNLOADED]

![image](https://github.com/user-attachments/assets/cebc0a8e-a95b-4e8c-a205-b5c2f79c172d)


18. Move the wordpress folder to the apache document folder by running "sudo mv wordpress/ /var/www/html"

![image](https://github.com/user-attachments/assets/355073bc-c3cc-473b-a9b4-66f1d5ed4f9d)


19. Navigate to http://\[Insert your elastic IP]/wordpress

![image](https://github.com/user-attachments/assets/8d6e9b1c-045e-4c90-91b3-7f3692837254)


20. Select "Let's Go!" on the launch screen before populating the text boxes with their corresponding credentials. Database Host should be set to "localhost", and Table Prefix should be set to "wp_"

![image](https://github.com/user-attachments/assets/8adedb89-9d0d-4224-ac39-4adb118718e4)


21. Copy the contents of the "**Configuration rules for wp-config.php**" text, either through the context menu or using Ctrl+A, then Ctrl+C

![image](https://github.com/user-attachments/assets/deb61127-8acf-4a9d-b22a-75dcb411e50d)


22. Configure the wp-config.php file
    
22a. Run "cd /var/www/html/wordpress" 

![image](https://github.com/user-attachments/assets/2fddf632-a9db-423b-b1d9-e2e164d83034)


22b. Run "sudo nano wp-config.php"

![image](https://github.com/user-attachments/assets/5f341db3-a9ab-4c59-940c-1cc9768c88f7)


22c. Paste the contents of your clipboard from **Step 21**

![image](https://github.com/user-attachments/assets/4501ae06-05c3-4ba1-b5c0-10a312601561)


22d. Write this using Ctrl+O, then pressing enter to confirm

![image](https://github.com/user-attachments/assets/26472326-77ac-4212-ab8c-154539e10b43)


23. Return to your WordPress browser tab, then click "Run the installation"

![image](https://github.com/user-attachments/assets/df6b6518-d576-4f25-886d-4326f8922008)'


24. Populate the contents of the text boxes. Ensure strong credentials are used, though

![image](https://github.com/user-attachments/assets/563d8b8a-6ecf-46be-abed-228d691cd702)


25. Confirm the details, then select log-in

![image](https://github.com/user-attachments/assets/89f7867e-973c-44ad-a3ec-b135bd850baa)


27. Enter your login credentials

![image](https://github.com/user-attachments/assets/79a249c4-f648-4003-b494-1af4b6eba915)


28. Run "cd /etc/apache2/sites-available/"

![image](https://github.com/user-attachments/assets/19d0e7ec-c32b-4527-9d54-33f15bdbe1e7)


29. Run "sudo nano 000-default.conf"

![image](https://github.com/user-attachments/assets/5659534c-98b5-45ed-a0b5-3911cbc16d52)


30. Locate the line "DocumentRoot /var/www/html" and change its contents to "DocumentRoot /var/www/html/wordpress"

![image](https://github.com/user-attachments/assets/f9169f86-b20f-4dc8-aed9-2a6299a1cef5)


32. Write this using Ctrl+O, then pressing enter to confirm

![image](https://github.com/user-attachments/assets/1da1a381-46aa-467e-90df-da0fe739d7ce)


33. Restart the server by running "sudo systemctl restart apache2"

![image](https://github.com/user-attachments/assets/ad2a157e-3e8d-4d8b-af1c-78eaee8977be)


34. Purchase and link a domain name. This documentation will use namecheap as an example, however similar steps will apply while purchasing from other providers.

34a. Sign-up for an account

![image](https://github.com/user-attachments/assets/d8837456-5151-43c1-a94e-f87fbd17fe2e)


34b. Search for a domain name you wish to use

![image](https://github.com/user-attachments/assets/5201b816-e39b-463f-a4c0-de4651f22a8a)


34c. Add the domain you wish to use to cart

![image](https://github.com/user-attachments/assets/3b75012f-dd5f-4c6c-ac93-b4cc61c2f1c6)


34d. Ensure domain registration is enabled before purchasing the domain

![image](https://github.com/user-attachments/assets/86c52240-22df-4312-bf74-1ec56d103c20)


34e. Navigate to your domain list and select "MANAGE"

![image](https://github.com/user-attachments/assets/88b2c2f7-619c-488d-af05-4a7b7e6a89a6)


34f. Select the "Advanced DNS" tile, and create 2 records. Ensure the type is "A Record", and that the Host for one is "@", and for the other is "www". The Value for both should be the Elastic IP address of the server, with TTL being set to automatic.


![image](https://github.com/user-attachments/assets/f704d6f6-6fc4-441a-8a75-a09195f8d462)


35. Return back to the WordPress dashboard, then navigate to the settings page.

![image](https://github.com/user-attachments/assets/66215a95-1695-44d8-a8de-ba5b4fe2a3ec)


36. Change the addresses at "WordPress Address (URL)" and "Site Address (URL)" from the elastic IP to http://\[YOUR DOMAIN NAME]

![image](https://github.com/user-attachments/assets/2d79f2ec-6ae4-4954-9681-36067bbfac50)


37. Run "sudo apt-get update" to ensure all your programs are up-to-date

![image](https://github.com/user-attachments/assets/ecc73bf1-0c29-4aca-be4d-3bb471632303)


38. Run "sudo apt install certbot python3-certbot-apache"

![image](https://github.com/user-attachments/assets/c656c9a3-d4db-4aa6-b390-c5fd59bdb161)


39. Run "sudo certbot --apache" and fill each dialog with the requested information

![image](https://github.com/user-attachments/assets/949c4d95-e8de-48b0-9858-aebb980ea9f2)


Your secure wordpress site should now be set-up!


**Script Documentation**

Note: This script was generated by ChatGPT. This is the original:

```
#!/bin/bash

# CONFIG
SITE_DIR="/var/www/html/wordpress"
BACKUP_DIR="/tmp/wp-backup"
REPO_DIR="$BACKUP_DIR/repo"
REPO_URL="git@github.com:yourusername/your-private-repo.git"
DB_NAME="your_db"
DB_USER="your_user"
DB_PASS="your_pass"

# CLEANUP
rm -rf "$BACKUP_DIR"
mkdir -p "$REPO_DIR"

# COPY FILES
rsync -a --exclude='wp-config.php' "$SITE_DIR/" "$REPO_DIR/"

# EXPORT DATABASE
mysqldump -u $DB_USER -p$DB_PASS $DB_NAME > "$REPO_DIR/db.sql"

# GIT OPERATIONS
cd "$REPO_DIR"
git init
git remote add origin "$REPO_URL"
git add .
git commit -m "Backup on $(date '+%Y-%m-%d %H:%M:%S')"
git push -f origin master
```



This is the modified version that was implemented in my server:

```
#!/bin/bash

# CONFIG
SITE_DIR="/var/www/html/wordpress"
BACKUP_DIR="/tmp/wp-backup"
REPO_DIR="$BACKUP_DIR/repo"
REPO_URL="git@github.com:WilliamTemby/Website-Backups.git"
DB_NAME="wordpress"
DB_USER="william"
DB_PASS="[REDACTED]"

# CLEANUP
rm -rf "$BACKUP_DIR"
mkdir -p "$REPO_DIR"

# COPY FILES
rsync -a --exclude='wp-config.php' "$SITE_DIR/" "$REPO_DIR/"

# EXPORT DATABASE
mysqldump --no-tablespaces  -u $DB_USER -p$DB_PASS $DB_NAME > "$REPO_DIR/db.sql"

# GIT OPERATIONS
cd "$REPO_DIR"
git init
git remote add origin "$REPO_URL"
git add .
git commit -m "Backup on $(date '+%Y-%m-%d %H:%M:%S')"
git push -f origin master
```

I also created another github repository that's visable at this address: https://github.com/WilliamTemby/Website-Backups/tree/master

The script, when run on a daily basis then commits the server's contents to this github repository as a backup system. A link to it, along with a screenshot of it in action is present on the home page of my site.


The "crontab -e" command was then used to automate this task on a daily basis:
![image](https://github.com/user-attachments/assets/9d994124-9ed8-4152-af3b-bea9782cb2f6)















 

















































**References (APA 7th)**

Tech Raj. 2022. “Create and Host a Wordpress Website on AWS EC2 with Your Own Domain Name!”
Youtu.be. Google. June 22, 2022. https://youtu.be/8Uofkq718n8.

