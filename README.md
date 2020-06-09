# AMI
## CSYE 6225 - Summer 2020

## Building Custom AMI using Packer

### Install Packer
- Download Packer from offical website HarshiCorp
- Unzip it in working directory
- Give it permission by running command chmod +x packer

### Build Instruction
- Pass the aws_access_ key & aws_secret_key of the IAM user, aws_region and subnet_id
- Run commands
-  ./ packer validate ami-template.json
- ./packer build \
       -var 'aws_access_key=REDACTED' \
       -var 'aws_secret_key=REDACTED' \
       -var 'aws_region=REDACTED' \
       -var 'subnet_id=REDACTED' \
       ami-template.json

### CI/CD
- Currently using Cirle CI tools to build new artifacts on each commit on GitHub
- Configure your webapp repository in Circle CI and follow the project
- Setup project environment variable for aws_access_key, aws_secret_key, aws_region and subnet_id