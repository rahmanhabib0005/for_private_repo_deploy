# for_private_repo_deploy
Step 1:-  ssh-keygen -t rsa -b 2048 -C username@serverdomain
Step 2:- touch ~/.ssh/config
Step 3:-  chmod 0600 ~/.ssh/config
Step 4:- chown username:username ~/.ssh/config
Step 5:- ssh -T git@github.com

# for_multiple_private_repo_deploy
Step 1:-  ssh-keygen -t rsa -b 2048 -C "username@serverdomain" -f ~/.ssh/new_project_rsa
Step 2:- eval "$(ssh-agent -s)"
      ssh-add ~/.ssh/new_project_rsa
Step 3:-  touch ~/.ssh/config
Step 4:- chmod 600 ~/.ssh/config
       chown username:username ~/.ssh/config
Step 5:- ssh -T github-new-project


#some git commands to up to date the site
1- git fetch origin
git reset --hard origin/main
2- git pull origin main
3- cd ~
4- mkdir -p public_html/git-deploy
