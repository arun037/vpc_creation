# Role Name - VPC Creation

A brief description of the role goes here.

Requirements
------------

- **Ansible version**: 2.10 or higher  
- **AWS CLI** installed and configured.  
- **boto3** and **botocore** Python libraries (required for AWS modules).  
  Install them using:  
  ```bash
  pip install boto3 botocore

Role Variables
--------------

The following variables can be customized to configure the VPC and its components:
vars/main.yml

vpc_name -	Name of the VPC	- my_vpc

vpc_cidr - 	CIDR block for the VPC - 10.0.0.0/16

public_subnets - List of public subnet CIDR blocks	- ["10.0.1.0/24"]

private_subnets -	List of private subnet CIDR blocks -	["10.0.2.0/24"]

region	- AWS region where the VPC will be created	- us-east-1

aws_access_key & aws_secret_access_key are encrypted using vault

Dependencies
------------

This role has no external dependencies. However, ensure that the following are set up:

AWS account with appropriate permissions.
Python libraries: boto3, botocore.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      roles:
         - { role: arun037.vpc_creation }

License
-------

BSD

Author Information
------------------

# Name: Arun
# MailID: marun2701@gmail.com

# **setup vault**
```
openssl rand -base64 2048 > ~/aws/ansible/vault.pass
```  


# **Encrypt string:**
```
ansible-vault encrypt_string  --name 'access_key' 'AKIAXXCCVFFGFFDDFFGGF' --vault-password ~/aws/ansible/vault.pass
```                                                                                       

```
ansible-vault encrypt_string  --name 'secret_key' 'AyDh36ZGLWXxlFGLSYShBCCDFFS' --vault-password ~/aws/ansible/vault.pass 
```
