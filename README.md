# Smart-Tactic
Smart Tactic 

Install
- **VS Code**

-  **GitHub**
1. Download Git https://git-scm.com/downloads and Run 
2. Set PATH in enviroenment variable (PATH location)

- **Terraform**
1. Download Terraform https://developer.hashicorp.com/terraform/install
2. UnZip folder - copy `terraform.exe` into a folder like `C:\Terraform\`
3. Add that folder to your system PATH
Search Environment Variable 
-> Edit/New -> `C:\Terraform`
4. Verify 
`terraform -version`
5. Even if couldn't able to find path
Close all powershell windows, Open powershell -> Run as administrator. 
Then run:
`setx PATH "$($env:PATH);C:\terraform" /M`
Verify: `terraform -version`

- **GCloud SDK**
1. Download GCloud SDK https://cloud.google.com/sdk/docs/install 
>> https://dl.google.com/dl/cloudsdk/channels/rapid/GoogleCloudSDKInstaller.exe
2. Run installer > Select Install GCloud CLI
3. Restart terminal
Verify: `gcloud --version`

- **Authenticate with GCP**
1. Run this in terminal 
`gcloud auth application-default login`
2. A browser window opens > Choose your google account
3. It saves credentials locally at `%APPDATA%\gcloud\`(Windows) OR `~/.config/gcloud/`(Mac).
4. To check GCP details 
command : `gcloud config list`
5. To check if we have project link with GCP
command : `gcloud config get-value project`
It will show if set, if not set your GCP project using *PROJECT_ID*
command : `gcloud config set project PROJECT_ID`
Then try again `step 4` and you will able to be `account` and `project`
6. Go to location where are terraform files are located
command : 
`terraform init`
`terraform plan -var="project_id=YOUR_PROJECT_ID"`
`terraform apply -var="project_id=YOUR_PROJECT_ID" -auto-approve`
--OR--
command : (If `project_id` is added in file `terraform.tfvars`)
`terraform init`
`terraform plan`
`terraform apply -auto-approve`

This is required for Terraform to talk to GCP
