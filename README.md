# Setting Up SSH for Private Repository Deployment

## Deploying to a Single Private Repository

### Step 1: Generate an SSH Key
```bash
ssh-keygen -t rsa -b 2048 -C "username@serverdomain"
```

### Step 2: Create SSH Config File
```bash
touch ~/.ssh/config
```

### Step 3: Set Permissions for Config File
```bash
chmod 0600 ~/.ssh/config
```

### Step 4: Change Ownership of Config File
```bash
chown username:username ~/.ssh/config
```

### Step 5: Test SSH Connection to GitHub
```bash
ssh -T git@github.com
```

---

## Deploying to Multiple Private Repositories

### Step 1: Generate a New SSH Key for the Project
```bash
ssh-keygen -t rsa -b 2048 -C "username@serverdomain" -f ~/.ssh/new_project_rsa
```

### Step 2: Add the New Key to the SSH Agent
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/new_project_rsa
```

### Step 3: Create SSH Config File (if not already created)
```bash
touch ~/.ssh/config
```

### Step 4: Set Permissions and Ownership for Config File
```bash
chmod 600 ~/.ssh/config
chown username:username ~/.ssh/config
```

### Step 5: Test SSH Connection for the New Project
```bash
ssh -T github-new-project
```

---

## Git Commands to Keep the Site Up-to-Date

### Fetch and Reset to Match Remote Repository
```bash
git fetch origin
git reset --hard origin/main
```

### Pull Latest Changes
```bash
git pull origin main
```

### Prepare Deployment Directory
```bash
cd ~
mkdir -p public_html/git-deploy
```
---
### Git works with specific ssh
```bash
GIT_SSH_COMMAND="ssh -i ~/.ssh/pub_ssh_name" git pull origin main
```
