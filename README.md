# Ansible playbook - Launch EC2 & Security-Group 

Home task for creating EC2 and 

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install foobar.

```bash
sudo apt update
sudo add-apt-repository ppa:deadsnakes/ppa 
sudo apt install python3
sudo apt install python3-pip -y
pip3 install ansible
pip3 install boto3
pip3 install awscli
```
Install Ansible
```bash
$ sudo apt update
$ sudo apt install software-properties-common
$ sudo add-apt-repository --yes --update ppa:ansible/ansible
$ sudo apt install ansible
## Usage
```

Install AWS-CLI
```bash
$ sudo apt install unzip
$ curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
```

## AWS configuration

You’ll need an AWS account with an IAM user to provision EC2 instances. These are made through: AWS Console > IAM > Add User, as seen below
Attach a policy for the user to be able to make changes on EC2 - I used AmazonEC2FullAccess. 
Copy the Access and Secret key and into a file on your local machine ~/.aws/credentials 

```bash
cd ~
mkdir .aws
cd .aws
touch credentials
```
edit the credentials file and add your AWS user Access and Secret key.

It should look like that:

```bash
[default]
aws_access_key_id = <your_access_key>
aws_secret_access_key = <your_secret_dkey>
```


## Contributing

Pull requests are welcome. 

## License

[MIT](https://choosealicense.com/licenses/mit/)
