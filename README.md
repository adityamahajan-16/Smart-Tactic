# Smart-Tactic
Smart Tactic 

Install
- VS Code

- Create GitHub account
1. Download Git and Run 
2. Set PATH in enviroenment variable

- Terraform
1. Download Terraform https://developer.hashicorp.com/terraform/downloads?utm_source=chatgpt.com
2. UnZip folder - copy '''terraform.exe''' into a folder like '''C:\Terraform\'''
3. Add that folder to your system PATH
    Search Environment Variable -> Edit/New -> '''C:\Terraform'''
4. Verify 
    '''terraform -version'''
5. Even if couldn't able to find path
    Close all powershell windows, Open powershell -> Run as administrator. Then run:
    "setx PATH "$($env:PATH);C:\terraform" /M"
    Verify: terraform -version

- GCloud SDK
1. Download GCloud SDK https://cloud.google.com/sdk/docs/install?utm_source=chatgpt.com
2. Run installer > Select Install GCloud CLI
3. Restart terminal
    Verify: gcloud version

- Authenticate with GCP
1. Run this in terminal 
    'gcloud auth application-default login'
2. A browser window opens > Choose your google account
3. It saves credentials locally at '~/.config/gcloud/' (Mac) OR '%APPDATA%\gcloud\' (Windows).

    This is required for Terraform to talk to GCP
