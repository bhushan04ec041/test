# Terraform-scripts

#create ec2 instance install the terraform with the below commands.\
sudo apt update\
sudo apt install curl\
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -\
sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"\
sudo apt-get install terraform\ 
which terraform\ 
terraform -version

#on workstation terraform we need to set the AWS credentials as a env variable, with the below commands.\
#using the env variable from the linux:\
#Step 1: export the env variable to linux.\
export TF_VAR_aws_access_key="XXXXXXXX"\
export TF_VAR_aws_secret_key="XXXXXXXXXx"\
export TF_VAR_region="XXXXXXXXXX"\
nano ~/.bashrc\
export TF_VAR_api_token="your_api_token_here"\
source ~/.bashrc\
echo $TF_VAR_api_token\
#Step 2: Use the variable as below in the script.\
access_key = var.aws_access_key\
secret_key = var.aws_secret_key\
region = var.region

#run the terraform commands in the project folder.\
$terraform init #for initialization\
$terraform fmt  #for formating the .tf files\
$terraform validate #for validating the resources\
$terraform plan -out state.tfplan #for creating the plan\
$terraform apply state.tfplan #for apply the plan\
$terraform destroy -auto-approve #to destroy the resources
