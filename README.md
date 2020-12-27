# Terraform

#### A terraform file that deploys an EC2 with apache2 installed on AWS.


The resources created to achieve that goal.

1. Create vpc
2. Create Internet Gateway
3. Create Custom Route Table
4. Create a Subnet 
5. Associate subnet with Route Table
6. Create Security Group to allow port 22,80,443
7. Create a network interface with an ip in the subnet that was created in step 4
8. Assign an elastic IP to the network interface created in step 7
9. Create Ubuntu server and install/enable apache2


## How to run

#### Install Terraform
  * `curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -`
  * `sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"`
  * `sudo apt-get update && sudo apt-get install terraform`

 > **Note:** Here is the official doc https://learn.hashicorp.com/tutorials/terraform/install-cli

#### Initialize Terrfaorm
  * Run `terraform init` to initialize terraform and install dependencies (providers)
  
#### Deploy configuration
  * Run `terraform apply -auto-approve` to deploy the infastructure on AWS
  
  
 > **Note:** Deployment will throw and error because its missing the `aws_secret_key`, `aws_access_key`, and `key_name`. Please fill them on the `terraform.tfvars` file with your credentials
