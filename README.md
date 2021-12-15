# AMI
# Description
This code base contains Hashicorp Packer code to initialize an AMI 

# Packages used
Hashicorp Packer

# Build Pipeline

1) git clone git@github.com:cloud-assignments-csye6225/ami.git into your working directory
2) Add buildAmi.sh script which contains all the input values that shall be assigned to the variables demanded by 'Builders' in ami.json
3) Run the script file -> ./buildAmi.sh
4) As the AMI is created, login to your aws console and check for the AMI that is created
5) Create and configure a new instance of this AMI 
    - Select appropriate VPC
    - Select appropriate subnet id
    - Configure a suitable security group for this instance
    - Assign a key pair or create a new key pair and store it on local machine (key_pair.pem)
    - Review and launch the instance
6) SSH into the instance
    - ssh -i key_pair.pem ubuntu@[instance_public_ip_address]
7) Copy code artifacts from local to EC2 instance using SCP command
    - SCP -i key_pair.pem -r [source] [destination]
    - source : path to artifacts on local machine
    - destination : ubuntu@[instance_public_ip_address]:/path
8) After copying the source files, install all necessary dependencies and databases on the server
9) Run the application on the EC2 instance and validate the application functionality

# Additional files required
1. buildAmi.sh - script with input values for AMI
2. source files containing the application 