

#Tools Used

* Configuration management - Chef
* Container - Docker
* CLI - AWS CLI

#Preparing Environment

## 1. Install AWS CLI
> sudo pip install awscli (If Python version is python2)
> sudo pip3 install awscli (If Python version is python3)
## 2. Configure AWS Credentials
> aws configure (Give inputs in each step)
  


## Domain Setting:
There are 2 files :
change-resource-record-sets.json: json object for domain metadata
modify-json.py: This file will update machine ip in json
Note: Before running create-instance you need to change domain name in change-resource-record-sets.json
 currently "Name": "test.test.com"
 to change domain add "Name": "newname.com"  

## Input Parameters for the script

imageid = 'Image ID of the AWS AMI'
instanceType = 'Type of Instance'
keypairName = 'Key pair through which the instance can be accessed'
securityGroup = Security group for the instance
subnetId = Subnet ID
tagKeyValue = Tag Name and Value (Eg  "Key=Name,Value=dev")
user='instance username'
pemfileLocation='location for aws pem file to do ssh'
chefLocation='.chef directory location to run bootstrap'

Run shell script: (There are 9 command line parameters need to pass)
 > sudo sh create-instance.sh "imageid" "instanceType" "keypairName" "securityGroup" "subnetId" "tagKeyValue" "user" "aws-pemfile-location" "chef-location"



 At last in browser type: test.test.com
  Wordpress home page will be shown.

