
- [ ] Create a Linux Vm on AWS Account



- [ ] Search for EC2 



- [ ] Create one AWS key to login to AWS ec2 instance 
- [ ] Click on Key Pairs

- [ ] Click on Create key


- [ ] Give the key and click on create key




- [ ] Click on Instances 



- [ ] Click on Launch Instance 

- [ ] Give name to vm using named tag



 - [ ] Select Ubuntu image


- [ ] Select Instance type (t2.micro)


- [ ] Select previously created key and then click on launch Instance 

- [ ] Login to Newly created vm
- [ ] Copy the public ip address assigned to vm and use below command

```
ssh -i <pemfile> ubuntu@<public ip address>
```

 - [ ] User names for diffrent OS

```
ec2-user for amazon Linux
ubuntu for ubuntu OS
```
- [ ] After login change the user to root

```
sudo -s
```
- [ ] Enable Password #PermitRootLogin prohibit-password 

```
sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes /etc/ssh/sshd_config
sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config

systemctl restart sshd

```
- [ ] Set the password for root user

```
passwd root

enter anny password of your choice
```

- [ ] Test to login to another vm using password and user

```

ssh root@private ip of another ip
```

- [ ] Update ubuntu OS

```
apt update
```
- [ ] Install Ansible 

```
apt install ansible 
```
- [ ] Check Ansible version

```
ansible --version
```

- [ ] Download Ansible config files to /etc/ansible/ 

```
mkdir -p /etc/ansible
cd /etc/ansible 
wget https://raw.githubusercontent.com/ansible/ansible/stable-2.9/examples/ansible.cfg
```


-  [ ] Start with Local host for test

```
ansible local -m ping --connection=local
```
- [ ] Create an inventory file

```
vi /etc/ansible/hosts

[test] 
Ip-address 
:wq
```
- [ ] Test with new vm
```
ansible test -m ping 
```
- [ ] Add below line to /etc/ansible/ansible.cfg

```
vi /etc/ansible/ansible.cfg
host_key_checking = false
```
- [ ] Install sshpass to use password with Ansible  

```
     apt install sshpass
     ansible test -m ping -u root -k
     ANSIBLE_HOST_KEY_CHECKING=False
     ansible test -m ping -u root -k
 ```

- [ ] Copy some file from one node to another node

```
ansible test -m copy -a "src=/tmp/new dest=/etc/" -u root -k
```
- [ ] Run linux linux with Ansible 

```
ansible test -m shell -a "ls -a" -u root -k
```
#### Tasks for everyone 

- [ ] Check memory available on all hosts
- [ ] Check disk size of all hosts
- [ ] check env on all hosts
- [ ] Change the permission of a file 
- [ ] check the size of a file


#### Start Again

- [ ] Install Apache 

```
ansible test -m apt  -a "name=apache2 state=present " -u root -k
```
- [ ] How to get ad hoc command help

```
ansible-doc <anycommand name>
```

- [ ] start the service 
```
ansible test -m service  -a "name=apache2 state=started" -u root -k
```

- [ ] Create index.html file 

```
vi index.html
Welcome to Ansible Session
```
- [ ] Copy Index.html file to another vm

```
ansible test -m copy  -a "src=/root/index.html dest=/var/www/html/" -u root -k
```
-  [ ] Test Apache in Browser

```
ip
```



##### Playbook Introductionn

- [ ] Know Yaml
- [ ] Create first playbook

- [ ] Install apache2 using playbook given below
```
---

- hosts: all
  tasks:
  - name: Install Apache2
    apt:
      name: apache2
      state: latest
  - name: check Apache  service status
    service:
      name: apache2
      state: started
  ````
  - [ ] run the above playbook

```
ansible-playbook  play.yaml  -u root -k
```

  - [ ] Check the syntax for Ansible 

```
ansible-playbook  play.yaml  --syntax-check
```
- [ ] Try Dry run

```
ansible-playbook  play.yaml  -C
```
- [ ] Check all hosts inside a playbook
- [ ] Install multiple software in one playbook
- [ ] Upgrade OS using Ansible 



#### Variable with Ansible Playbook






- [ ] How to define variable in Ansible playbook

```
- hosts: all
  vars:
     pack: apache2
  tasks:
  - name: Install Apache2
    apt:
      name: "{{ pack }}"
      state: latest
  - name: check Apache  service status
    service:
      name: apache2
      state: started
      
     
   ```
   
   
   
   ## Optional if you want to try with ssh key in place of Password
   
   - [ ] Create ssh key on Ansible controller

```
ssh-keygen    press enter twice 
```

- [ ] Send the ssh public to another vm

```
ssh-copy-id <vm ip>
```

Now You will be able to rub Ansible commdnds without password .



Happy Learning 



