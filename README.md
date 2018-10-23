# GitHub Tutorial

_by_ **Anonymous**

<br>
---
## Git vs. GitHub 
**Git:**
- Version control; manage the changes made to your repositories and/or files
- You do **NOT** need github for git to work

**Github:**
- Stores your files and/or repositories in the cloud
- You can see and track what changes you made to your files and/or repositories
- Allows multiple people to collaborate on file(s)
- You **NEED** git for github to work


---
# Initial Setup
### Setting up your github account
1. Go to [github.com](https://github.com/)  
2. On the top right cornor, click **Sign up**  
3. Fill out your:  
    - **Username**  
    - **Email Address**  
    - **Password**
4. Choose your personal plan (I'm choosing the free plan cause I'm broke) and then
click **Continue**  
5. Fill out the experience survey or skip it (Doesn't matter)
6. You should be redirected to your github homepage by now. If not just go to [github.com](https://github.com/)

### Setting up your SSH key
1. Go to [github.com](https://github.com/)
2. **Sign in** if you didn't
3. Click on your little icon
4. Go to **Setting**
5. Underneath **Personal settings** click **SSH and GPG keys**
6. Underneath **SSH keys** click **New SSH key**
7. Type in your title underneath **Title** (**"cloud9"** for instance)
8. For **Key** do the following steps  
    - Go to your cloud9 home page  
    - Click the **gear icon** on the top right of the page  
    - Click **SSH Keys** underneath **ACCOUNT**  
    - Copy the code underneath **Connect to your private git repository**(it should start with ssh-rsa, and make sure you copied everything)
    - Go back to your github tab and paste everything underneath **Key**  
    - Click **Add SSH Key** 
9. Go to your cloud9 workspace
10. Type in ```ssh -T git@github.com``` into your console 
11. If your console replied **_"Hi (your username)! You've successfully authenticated, but GitHub does not provide shell access"_** it means that you've finish setting up your SSH Key and your cloud9 is now connected to your github. But if the console didn't reply back this, then repeat steps 1 through 11 underneath **Setting up your SSH key** and try again.


---
# Repository Setup
### Initialize git in cloud9
1. cd into the repository that you want to initialize git in
2. Type in ```git init``` into the consoleq


---
# Workflow & Commands
After you have finish modified your file or just want to commit to save your work...
1. Type ```git add .``` into your console
2. Type in ```git status``` to make sure that the file you want to commit is in green
3. Type in ```git commit -m "(commit message)"``` into your console
4. Type in ```git push -u origin master``` if this is your first time pushing to your remote and just ```git push``` if you've already type in ```git push -u origin master``` before



---
# Rolling Back Changes
## (Always keep in mind to cd into the repository that you're working in)
### Undo edits
1. Type in ```git checkout -- (filename)``` into your console 

### Undo add
1. Type in ```git reset HEAD (filename)``` after you've added your file(s) to staging area.  
(You can check if your file is in staging or not by typing ```git status``` into your console. If your **modified** file is in green, it means that your file is in the staging area. If your **modified** file is highlighted in red then your file is not in staging area)

### Undo commit
1. Type in ```git reset --soft HEAD~1``` into your console, and it should go back to your previous commit

### Undo push
1. Type in ```git log``` and find the commit you want to go back to
2. Copy the commit **sha**
3. Press **q** to quit
4. Type in ```git revert (sha code)``` and you should be in that commit