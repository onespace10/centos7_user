# dockerfiles-centos7-user-addable

Centos7, It support base user creation and password setting.

# Building & Running

Copy the sources to your docker host and build the container, and to run on windows

```
docker build --tag daya123/centos7 ./ 
docker run -it --rm -v C:\\Users\\home\\centos7_user:/df --name c1 -e USER=daya123 -e PASSWD=daya123 daya123/centos7
```

To install git on centos7

```
yum install git
```

Generating public/private ed25519 key pair

```
ssh-keygen -t ed25519 -C "My-Email@gmail.com"
Enter file in which to save the key (/root/.ssh/id_ed25519): /root/.ssh/ed25519
Enter passphrase (empty for no passphrase): 
Enter same passphrase again:
Your identification has been saved in ed25519.
Your public key has been saved in ed25519.pub.
The key fingerprint is:
ssh-ed25519 AAAAC3N... MY-Email@gmail.com
...
```

On GitHub
github.com -> Sined in as MY-Name -> Settings -> SSH Keys -> New SSH Key

To confirm You've successfully authenticated

```
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/ed25519
ssh-add -l
ssh -T git@github.com   
Hi MY-Name! You've successfully authenticated, but GitHub does not provide shell access.

```

To set your global username/email configuartion

```
git config --global user.email "My-Email@gmail.com"
git config --global user.name "MY-Name"
```

Pushing commits to a remote repository

```
…or create a new repository on the command line
echo "# centos7_user" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:MY-Name/centos7_user.git
git push -u origin main

…or push an existing repository from the command line
git remote add origin git@github.com:MY-Name/centos7_user.git
git branch -M main
git push -u origin main

…or import code from another repository
You can initialize this repository with code from a Subversion, Mercurial, or TFS project.


git push git@github.com:MY-Name/centos7_user.git
```
