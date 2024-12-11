# for_private_repo_deploy
Step 1:-  ssh-keygen -t rsa -b 2048 -C username@serverdomain
Step 2:- touch ~/.ssh/config
Step 3:-  chmod 0600 ~/.ssh/config
Step 4:- chown username:username ~/.ssh/config
Step 5:- ssh -T git@github.com
