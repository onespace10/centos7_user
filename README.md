# dockerfiles-centos7-user-addable
Centos7, It support base user creation and password setting.
# Building & Running
Copy the sources to your docker host and build the container, and to run on windows
```
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
git init
git add .
git commit -m "centos7_user first commit"
git push git@github.com:MY-Name/centos7_user.git
```
