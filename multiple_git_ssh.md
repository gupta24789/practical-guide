
## Instruction

1. Generate the ssh key. 
    - **t** : specify the alogothim used to generate ssh key
    - **C** : comments
    - **f** : username (keys will be created using this name only)

```
Account-1 : ssh-keygen -t rsa -C "csit.saurabh@gmail.com" -f "saurabh"
Account-2 : ssh-keygen -t rsa -C "test@gmail.com" -f "test"
```

2. Copy the content of saurabh.pub & test.pub to corresponding github account under setting -> ssh key -> add new key
```
Name : admin (you can give any title)
Path : https://github.com/settings/ssh/new
```

3. Add ssh keys to ssh Agent
```
ssh-add ~/.ssh/saurabh
ssh-add ~/.ssh/test
```

4. Create the config file.
```
cd ~/.ssh
touch config
```

5. Add the config for every account
```
Host saurabh
	HostName github.com
	User git
	IdentityFile ~/.ssh/saurabh

Host test
	HostName github.com
	User git
	IdentityFile ~/.ssh/test
```

6. Clone repo

- github ssh path : git@github.com:gupta24789/KnowledgeBase.git
- Replace git@github.com with your Host name in the config file


```
git clone saurabh:gupta24789/KnowledgeBase.git
```

```
git clone test:gupta24789/KnowledgeBase.git
```


7. Check the git remote 
```
git remote -v
```

8. For new directory initialize the user name and email 
```
git config user.name "saurabh"
git config user.email "csit.saurabh@gmail.com"
```
