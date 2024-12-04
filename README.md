# Guide for Cloning a Private GitHub Repository and Managing Branches

This guide provides a step-by-step process to help you authenticate with GitHub, clone a private repository, and manage branches effectively.

### 1. Authentication Options

To clone a private repository, proper authentication is essential. Below are the recommended methods for authentication.

#### **Option 1: HTTPS with Personal Access Token (PAT)**

1. **Generate a Personal Access Token (PAT)**:
   - Go to **GitHub > Settings > Developer Settings > Personal Access Tokens**.
   - Click on **Generate new token**.
   - Select the appropriate scopes, such as `repo` for repository access.
   - Copy the generated token (you won't be able to see it again).

2. **Clone the Repository**:
   - Use the token in your clone command as shown below:
     ```sh
     git clone https://<YOUR_GITHUB_USERNAME>:<YOUR_PERSONAL_ACCESS_TOKEN>@github.com/KvellDynamics/rmb-chatbot-backend.git "d:\Work Area\Azure DevOps-Organization\rmbchatbot-backend\rmb-chatbot-backend" --progress
     ```
   - Replace `<YOUR_GITHUB_USERNAME>` and `<YOUR_PERSONAL_ACCESS_TOKEN>` with your GitHub username and generated token, respectively.

#### **Option 2: SSH Key Authentication**

1. **Add Your SSH Key to GitHub** (if not already done):
   - Go to **GitHub > Settings > SSH and GPG keys** and add your SSH public key.

2. **Clone Using SSH**:
   - Use the following command to clone the repository:
     ```sh
     git clone git@github.com:KvellDynamics/rmb-chatbot-backend.git "d:\Work Area\Azure DevOps-Organization\rmbchatbot-backend\rmb-chatbot-backend" --progress
     ```
   - Ensure that your SSH agent is running and your SSH key is loaded before cloning.

### 2. Confirm the Repository URL

Before cloning, ensure that the repository URL is correct and accessible:
- You can visit the repository URL in a web browser to verify that it is available.
- Example URL: `https://github.com/KvellDynamics/rmb-chatbot-backend.git`

### 3. Managing Branches

After cloning the repository, you may need to switch to a specific branch. Below are the steps for managing branches effectively.

#### **Option 1: Switch to a Branch After Cloning**

1. **Navigate to Your Project Directory**:
   ```sh
   cd "d:\Work Area\Azure DevOps-Organization\rmbchatbot-backend"
   ```

2. **Fetch All Branches** (if they are not available locally):
   ```sh
   git fetch
   ```

3. **Switch to the Desired Branch** (e.g., `present-trail`):
   ```sh
   git checkout present-trail
   ```

#### **Option 2: Switch to a Specific Branch for Running Locally**

If you want to switch from `present-trail` to `present-3.0.0`:

1. **Confirm the Current Branch**:
   ```sh
   git branch
   ```
   This command will show the current branch you are on.

2. **Switch to the `present-3.0.0` Branch**:
   ```sh
   git checkout present-3.0.0
   ```
   - If the branch does not exist locally:
     ```sh
     git fetch origin
     git checkout present-3.0.0
     ```
   These commands will fetch the latest branch information from the remote repository and switch to the specified branch.

### Summary

This guide provides a straightforward approach to authenticate, clone a private repository, and switch between branches:
- Use HTTPS with a Personal Access Token (PAT) or SSH keys for authentication.
- Confirm the repository URL before cloning.
- Use `git fetch` and `git checkout` commands to switch between branches effectively.

Feel free to refer to this guide whenever you need to manage a private repository on GitHub!

