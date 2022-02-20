# setup ansible ubuntu
Install ansible at control machine:
```sh
sudo apt-add-repository ppa:ansible/ansible -y
sudo apt update -y
sudo apt install ansible -y
```
Create devops user at control machine
```sh
sudo adduser devops
sudo usermod -aG sudo devops
su devops
cd ~
ssh-keygen
```
Make sure current user as devops
```sh
whoami
```
devops

```sh
git clone https://github.com/sonnyyu/setupansibleubuntu
cd setupansibleubuntu
```
Edit hosts-dev with IP address
```sh
[webservers]
app1 ansible_host=192.168.1.2
app2 ansible_host=192.168.1.3
```
Run Playbook
```sh
ansible-playbook playbook.yml -usonnyyu -bK --ask-pass
```
Test password less ssh login
```sh
ansible-playbook  checkpwless.yml
```

