# How to Create a GitHub Account, Repository, and Personal Access Token (PAT)

This guide will walk you through setting up a GitHub account, creating a repository, and generating a Personal Access Token (PAT) to use Git from your local machine.

---

## 1. Create a GitHub Account

### Steps:
1. Go to [GitHub](https://github.com/).
2. Click the **Sign Up** button at the top-right corner.
3. Fill in the following details:
   - **Email Address**: Enter your email.
   - **Username**: Choose a unique username.
   - **Password**: Create a strong password.
4. Solve the CAPTCHA, then click **Create Account**.
5. Verify your email by clicking the link sent to your inbox.
6. Follow any additional steps to personalize your profile.

---

## 2. Create a New Repository

### Steps:
1. Once logged in, click the **+** icon in the top-right corner.
2. Select **New Repository**.
3. Fill out the repository details:
   - **Repository Name**: Enter a name for your project (e.g., `my-first-repo`).
   - **Description (Optional)**: Add a short description of your project.
4. Choose the repository's visibility:
   - **Public**: Anyone can see your repository.
   - **Private**: Only you and collaborators can see it.
5. (Optional) Check **Add a README file** if you want a basic introduction file in your repository.
6. Click **Create Repository**.

---

## 3. Generate a Personal Access Token (PAT)

### What is a PAT?
A **Personal Access Token (PAT)** acts as a password when accessing your GitHub account via the command line.

### Steps to Generate a PAT:
1. Go to [GitHub Settings](https://github.com/settings/profile).
2. Scroll down to **Developer Settings** and click it.
3. Click on **Personal Access Tokens** > **Tokens (classic)**.
4. Click **Generate new token** > **Generate new token (classic)**.
5. Fill out the token details:
   - **Note**: Enter a description like `My PAT`.
   - **Expiration**: Choose when the token should expire (e.g., 30 days, 60 days, or no expiration).
   - **Scopes**: Select the permissions the token needs. For basic Git operations, check:
     - `repo` (Full control of private repositories).
     - `workflow` (Access to workflows).
     - `write:packages` (Push to GitHub Packages).
6. Click **Generate Token**.
7. Copy the token immediately. Once you leave this page, you cannot view it again.

---

## 4. Save the PAT Locally

### Option 1: Save the PAT in a Secure File
1. Open a terminal or command prompt.
2. Navigate to your home directory:
   
   ```bash
   cd ~
   ```
## Create a .git-credentials file
```
touch .git-credentials
```
## Open the file with a text editor
```
nano .git-credentials
```
## Add the following content (replace <your-username> and <your-pat>):

```
https://<your-username>:<your-pat>@github.com
```
## Save and exit:
In Nano: Press Ctrl+O to save and Ctrl+X to exit.

# Option 2:  Cache the PAT Globally

## Enable credential caching:
```
git config --global credential.helper store

```
- Perform a Git operation like git push, and you’ll be prompted for your username and PAT. Once entered, it will be saved for future use.

## Example Workflow

Here’s how to use your PAT and repository:
  ### Clone your repository:
  
```
git clone https://github.com/<your-username>/<repo-name>.git

```
### Make changes and commit:
 ```
 git add .

 git commit -m "Initial commit"

 ```
### Push to GitHub
```
git push

```
### Enter your username and PAT when prompted (only needed once if cached).