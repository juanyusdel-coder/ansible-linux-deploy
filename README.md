This project uses Terraform to provision the AWS infrastructure (VPC, Security Groups, EC2) and 
Ansible to configure the server (installing software, hardening, and setup) via GitHub Actions.

Setup Instructions
AWS Key Pair: Create an SSH Key Pair in AWS named deployer-key. Save the .pem file.
GitHub Secrets: In your repo, go to Settings > Secrets > Actions and add:
AWS_ACCESS_KEY_ID: Your IAM user key.
AWS_SECRET_ACCESS_KEY: Your IAM secret key.
AWS_SSH_KEY: The contents of your deployer.pem file.
Push to GitHub: Once you push these files, GitHub Actions will:
Create the EC2 instance.[3][4][5][6][7]
Wait for it to be ready.[5][7]
Connect via SSH and install Nginx using Ansible
