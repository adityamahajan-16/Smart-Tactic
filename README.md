# Smart-Tactic
Smart Tactic 
> **Note**- All numbers are considered as steps

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
It will show if set, if not set your GCP project using **PROJECT_ID**  
command : `gcloud config set project PROJECT_ID`  
Then try again **step 4** and you will able to be **account** and **project**
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

--------------------------------------------------------------------------------------------------------------

**GitHub Branching Stratergy**:

1. Create Repository  
Create **GitHub account** and **New repository** and initialize with the **README.md**  
`main` -> Production
`develop` -> Staging 

2. Create Base Branches  
Create `develop` branch (Staging)  
`git clone "GITHUB Repository link"`      
`git checkout -b develop`  

3. Create Branch Protection Rules  
- Branch Ruleset for `develop`/`main`  
- Setting >> Branches >> Add Branch Rulset  
- Rulset Name  
- Target Branches >> Add Target >> Include by Pateern >> `develop`  
- Select Checks:  
    1. Require a pull request (PR) before merging atleast 2 reviewers  
    2. Require review from Code Owners  
    3. Require conversation resolution before merging  
    4. Allowed merge methods (Merge, Squash, Rebase)  
    5. Require Status Checks to pass (Optional)  
    6. Block force pushes  
- Click on **Create**  

--------------------------------------------------------------------------------------------------------------

**Quick Git Reference Handbook**  

1. *SetUp & COnfiguration*  
- `git config --global user.name "Your Name"` : Set Your Name  
Verify : `git config user.name`  
- `git config --global user.email "you@example.com"` : Set Your Email  
Verify : `git config user.email`  
- `git config --list` : Check Current Config  

2. *Repository Initialization*  
- `git init` : Initialize New Git Repo  
- `git clone <repo-URL>` : Clone an existing repo on GitHub  

3. *Basic Workflow*  
- `git status` : Show Repo Status (Stage/Unstaged/Untracked files)  
- `git add .` : Stage all changes   
- `git add <file>` : Stage Changes  
- `git commit -m "update message"` : Commit Staged Changes  

4. *Branching & Merging*  
- `git branch` : List Branches  
- `git branch <Branch Name>` : Create New Branch
- `git checkout -b <Branch Name>` : Create and Switch to Branch  
- `git checkout <Branch Name>` : Switch to Branch  
- `git merge <Branch Name>` : Merge Branch into Current Branch  
- `git branch -d <Branch Name>` : Delete the Branch  

5. *Remaote Repositories*
- `git remote -v` : Show Remotes  
- `git remote add origin <URL>` : Add Remote  
- `git push origin <Branch Name>` : Push Branch to Remote  
- `git pull origin <Branch Name>` : Pull Latest Changes  
- `git fetch` : Fetch Updates (Without merging)  

6. *Viewing History*  
- `git log` : Commit History  
- `git log --oneline --graph --all` : Compact History with Branches  
- `git diff` : Show Unstaged Changes  
- `git diff --staged` : Show Staged Changes  

7. *Undo & CleanUp*
- `git restore <File Name>` : Undo Changes in Working Directory  
- `git restore --staged <File Name>` : Unstaged File  
- `git reset --hard <Commit ID>` : Reset Repo to Commit ID, but delete Uncommited Work  
- `git revert <Commit ID>` : Create a New Commit that undoes a Commit ID  




  



