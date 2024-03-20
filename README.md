# Ansible playbook - Launch EC2 & Security-Group 

Home task - Launching EC2 with Security-Group

## Prerequisites 
Local Ubuntu machine (tested on v22.04 & v20.04)

Make sure you have all the prerequisites installed (Python3 and Python Modules). 
```bash
$ sudo apt update
$ sudo add-apt-repository ppa:deadsnakes/ppa 
$ sudo apt install python3
$ sudo apt install python3-pip -y
$ pip3 install boto3
```
Install Ansible
```bash
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
```

Install AWS-CLI
```bash
$ sudo apt install unzip
$ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```
Check Git is installed
```bash
git --version
```
## AWS configuration

You’ll need an AWS account with an IAM user to provision EC2 instances. These are made through: AWS Console > IAM > Add User, as seen below
Attach a policy for the user to be able to make changes on EC2 - I used AmazonEC2FullAccess. 
Paste the Access and Secret key and into ~/.aws/credentials file on your local machine.
If you don't have one, create it:
```bash
cd ~
mkdir .aws
cd .aws
touch credentials
```
Edit the credentials file and add your AWS user Access and Secret key.

It should look like that:

```bash
[default]
aws_access_key_id = <your_access_key>
aws_secret_access_key = <your_secret_dkey>
```
Make sure you have a VPC with a subnet routing to igw.

Create SSH key for the Key Pairing for the EC2
```bash
$ ssh-keygen -t rsa -b 4096 -f ~/.ssh/my_aws # keep the passphrase empty
$ chmod 400 ~/.ssh/my_aws
```

## Usage
 Clone the repo into your user home folder which you created the SSH key with:
```bash
$ cd ~
$ git clone https://github.com/kobiba007/ec2launch.git
$ cd ec2launch
```
Run the playbook

```bash
$ ansible-playbook ec2launch.yml
```
Now you can SSH to the machine:
```bash
ssh -i "~/.ssh/my_aws" ec2-user@<ec2-public-ip> 
```
Done :)

## Contributing

Pull requests are welcome. 
