Step-by-Step Guide
Part 1: Create an AWS Account
Visit AWS Website

Go to the AWS website at https://aws.amazon.com.
Sign Up for an AWS Account

Click on the "Create an AWS Account" button.
Enter your email address and set a password for your new AWS account.
Enter Account Information

Provide your full name or company name, and other necessary information.
Choose the "Personal" or "Professional" account type based on your needs.
Provide Payment Information

Enter your credit card or other payment information. Note that AWS offers a free tier, but you still need to provide payment details.
Identity Verification

Confirm your identity by providing your phone number. You will receive a call or text with a verification code.
Select Support Plan

Choose the Basic support plan, which is free. More comprehensive support plans are available at additional cost.
Complete the Registration

Review and complete the registration process. You will receive a confirmation email from AWS.
Part 2: Set Up a Basic EC2 Instance
Log In to AWS Management Console

Go to the AWS Management Console at https://console.aws.amazon.com.
Log in with your AWS credentials.
Navigate to EC2 Dashboard

In the AWS Management Console, search for "EC2" and click on the EC2 service.
Launch a New Instance

Click on the "Launch Instance" button to start the instance creation process.
Choose an Amazon Machine Image (AMI)

Select the "Amazon Linux 2 AMI" (free tier eligible) for this setup.
Choose an Instance Type

Select the "t2.micro" instance type, which is eligible for the free tier.
Configure Instance Details

Click "Next: Configure Instance Details" and keep the default settings.
Add Storage

Click "Next: Add Storage" and keep the default storage settings.
Add Tags

(Optional) Add a tag to your instance for easier identification. For example, set the key to Name and the value to MyFirstInstance.
Configure Security Group

Click "Next: Configure Security Group".
Create a new security group with the following rule:
Type: SSH
Protocol: TCP
Port Range: 22
Source: Anywhere (0.0.0.0/0)
Review and Launch

Click "Review and Launch" to review your settings.
Click "Launch".
Select a Key Pair

Select "Create a new key pair".
Provide a name for your key pair (e.g., my-key-pair).
Download the .pem file to a secure location, as you will need it to access your instance.
Launch the Instance

Click "Launch Instances".
Once the instance is launched, click "View Instances" to go to the instance dashboard.
Part 3: Deploy a Sample Python Script
Connect to Your EC2 Instance

Locate your instance in the EC2 dashboard and select it.
Click "Connect" and follow the instructions to connect via SSH. For example:
shell
Copy Code


ssh -i /path/to/my-key-pair.pem ec2-user@<Your_Instance_Public_IP>
Install Python

Verify if Python is installed by running:
shell
Copy Code


python3 --version
If not installed, install it using:
bash
Copy Code


sudo yum install python3 -y
Create a Python Script

Use a text editor to create a new Python file. For example:
shell
Copy Code


nano add_two_numbers.py
Add the following content to the file:
python
Copy Code


def add_two_numbers(a, b):
    return a + b

if __name__ == "__main__":
    result = add_two_numbers(3, 5)
    print(f"Result: {result}")
Save and exit the editor (Ctrl+X, Y, Enter).
Run the Python Script

Run the script using:
shell
Copy Code





