- [ ] Open the vscode 
- [ ] create a file provider.tf

```
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
      version = "4.64.0"
    }
  }
}

provider "aws" {
  region     = "us-east-1"
  access_key = "copy from your aws account "
  secret_key = "copy from your aws account"
  token = "<copy from your aws account>"
}
```
- [ ] run the below command

```
terraform init
```

- [ ] Create another file

```
resource "aws_instance" "web" {
  ami           = "ami-02396cdd13e9a1257"
  instance_type = "t2.micro"

  tags = {
    Name = "HelloWorld"
  }
}
```


- [ ] Run the below command to check what your code will do

```
terraform plan
```

- [ ] Execute your code to create vm

```
terraform apply
```
- [ ] Create a key with name test

- [ ] Code for key

```
resource "aws_instance" "web" {
  ami           = "ami-007855ac798b5175e"
  instance_type = "t2.micro"
  key_name =  "test"

  tags = {
    Name = "HelloWorld"
  }
}
```

- [ ] Now try to login

```
ssh -i <pemfile> ubuntu@ip
```





# ELK Stack for Logging on Lab VM


- [ ] Download the code using below commands

```
sudo su
cd 
git clone https://github.com/Siraj-ul-muneera/ELKExample.git
cd ELKExample
ls -alrt

```
![image](https://user-images.githubusercontent.com/120269399/233933266-d29a4342-b6b2-49af-8e64-90fc951553ae.png)


- [ ] Install docker compose

```
apt install docker-compose
docker-compose version

```
 - [ ] Set max map for elasticsearch to work properly

```
sysctl -w vm.max_map_count=262144
```
- [ ] Remove the files to upgrade OS

```
cd /etc/apt/sources.list.d/
rm -rvf kubernetes.list* google-chrome.list* jenkins.list*
```
- [ ] remove docker completly .
```
systemtcl unmask docker
apt remove docker*

init 6
```
- [ ] 	Run the docker-compose command to initialize the ELK stack.
```
sudo -s
cd 
cd ELKExample
docker-compose up -d
```
 - [ ] Check running containers

```
docker ps 
```
 - [ ] Open Kibana using below

```
http://localhost:5601/app/kibana
```

 - [ ] Configure Jenkins pipeline for Docker build and deployment
 - [ ] From the browser, navigate to http://localhost:8080 and login to Jenkins
 - [ ] 	2.2	Configure your Docker hub credentials in Jenkins. Go to Manage Jenkins -> Manage Credentials -> click on Jenkins link -> click on Global credentials (unrestricted) -> click on Add Credentials from the left pane.
 ![image](https://user-images.githubusercontent.com/120269399/233934312-7bbd88bc-711b-4497-8dd3-aec98d8ceb47.png)


- [ ] Add creds as below

```
2.3	Add the details as shown below
Username: <Your_DockerHub_Username>
Password: <Your_DockerHub_Password>

```
![image](https://user-images.githubusercontent.com/120269399/233934461-20be5aa1-f899-4139-8545-75345080f17e.png)


- [ ] Create a pipeline


![image](https://user-images.githubusercontent.com/120269399/233934554-14681fd4-075f-40d4-90f2-d486dfc3d13b.png)

- [ ] 2.6	You can either use the below git repository or Fork it in your Github account and use it
```
https://github.com/Siraj-ul-muneera/ELKExample.git
```
![image](https://user-images.githubusercontent.com/120269399/233934797-9d165558-c6d1-4468-b347-1c3149ce8ec4.png)

- [ ] 2.8	Give 777 permission to the Docker sock file since we are running Docker command from a Jenkins user.

```
chmod 777 /var/run/docker.sock
```

 - [ ] Click on Deploy


![image](https://user-images.githubusercontent.com/120269399/233934994-3e93d3e6-e96f-422f-a046-de8427c74396.png)






