Student name: William Temby

Student ID: 35578349

Domain name: https://williamtemby171.com/

Video explainer: https://murdochuniversity-my.sharepoint.com/:v:/g/personal/35578349_student_murdoch_edu_au/EYY1uOOoaKNAt4svqqtdnK0BhN78-BI77gbxe6MtRMSWCQ?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJPbmVEcml2ZUZvckJ1c2luZXNzIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXciLCJyZWZlcnJhbFZpZXciOiJNeUZpbGVzTGlua0NvcHkifX0&e=MZDmJS

(Note: this requires you to be signed into a Murdoch account in order to view)



**Server setup documentation**

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






**VM setup:**




**References (APA 7th)**

Tech Raj. 2022. “Create and Host a Wordpress Website on AWS EC2 with Your Own Domain Name!”
Youtu.be. Google. June 22, 2022. https://youtu.be/8Uofkq718n8.

