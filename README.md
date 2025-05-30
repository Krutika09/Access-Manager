
# GitHub Repository Access Manager

A shell script for DevOps engineers to list users with read access to a GitHub repository using the GitHub REST API. This tool helps efficiently manage collaborators and ensure former team members no longer have access.

## 🔧 Features

- Lists GitHub users with read (`pull`) access to a specific repository.
- Uses GitHub REST API v3.
- Helps audit repository access daily without manually logging in.

##  Prerequisites

- GitHub Personal Access Token (Classic)
- `curl`, `jq`, and `bash` installed on your machine
- GitHub username and organization repository details
- Create an **Organization** on GitHub
  * You must be signed in to your **GitHub account**.
### Steps:

1. **Go to GitHub**
   Visit: [https://github.com](https://github.com) and log into your account.

2. **Open Your Profile Menu**
   In the top-right corner, click your **profile picture**.

3. **Select "Your organizations"**
   From the dropdown menu, choose **"Your organizations"**.

4. **Click "New organization"**
   On the organizations page, click the **"New organization"** button.

5. **Choose a Plan**

   * **Free**: Great for open source or small teams.

6. **Enter Organization Details**

   * **Organization name**: e.g., `my-devops-team`
7. **Invite Team Members** (Optional)

   * You can invite team members by entering their GitHub usernames or emails.
   * You can also **skip** this step and add members later.

8. **Review and Create**
   * Confirm the details.
   * Click **"Create organization"**.

###  After Creation:
* You'll be redirected to the organization dashboard.
* From here, you can:
  * Create repositories
  * Set up teams and permissions

##  Generate GitHub Token

1. Go to **GitHub > Settings > Developer Settings > Personal Access Tokens (classic)**.
2. Click **"Generate new token (classic)"**.
3. Set a note, select required scopes (e.g., `repo` or `read:org`), and generate the token.
4. Copy and store the token securely.

## 🛠️ Setup

### 1. Export GitHub credentials

```bash
export username="your_github_username"
export token="your_personal_access_token"
````

### 2. Create the script file

Create a file `list-users.sh` and add the following:

### 3. Make script executable

```bash
chmod +x list-users.sh
```

### 4. Run the script

```bash
./list-users.sh <REPO_OWNER> <REPO_NAME>
```

Replace `<REPO_OWNER>` and `<REPO_NAME>` with the respective GitHub organization/username and repository name.

![image](https://github.com/user-attachments/assets/5aba8948-31c7-4772-af5a-abceef8a0e31)

##  Example

```bash
./list-users.sh DevopsOrg09 Shell-Project
```

##  Security Note

* **Never hardcode your personal access token in scripts.**
* Use environment variables or secret managers instead.
* Revoke and regenerate your token if accidentally exposed.
