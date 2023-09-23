# Using multiple SSH Keys

### Generate an SSH key:
```
ssh-keygen -t rsa -C <email1@example.com>

````

### Generate another SSH key:
```
ssh-keygen -t rsa -f ~/.ssh/accountB -C <email2@example.com>

````

### Now, two public keys (id_rsa.pub, accountB.pub) should be exists in the ~/.ssh/ directory.
```

ls -l ~/.ssh     # see the files of '~/.ssh/' directory

````

### Create configuration file ~/.ssh/config with the following contents:
```
nano ~/.ssh/config

````
```
 Host bitbucket.org
     User git
     Hostname bitbucket.org
     PreferredAuthentications publickey
     IdentityFile ~/.ssh/id_rsa

 Host bitbucket-accountB
     User git
     Hostname bitbucket.org
     PreferredAuthentications publickey
     IdentitiesOnly yes
     IdentityFile ~/.ssh/accountB
```

### Clone from default account.
```

git clone git@bitbucket.org:username/project.git

````

### Clone from the accountB account.
```
git clone git@bitbucket-accountB:username/project.git

````
> Note: Because of the User git directive, you can omit the git@ portion of the repo URL, shortening your clone command like so:
```
git clone bitbucket-accountB:username/project.git

````
This is the only purpose of that directive. If you don't need it (e.g. you always copy-paste the git clone command from the website), you can leave it out of the config.
