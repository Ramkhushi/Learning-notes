- [ ] How to check current user ?

```
whoami
```
- [ ] How to check ip address ?
```
ifconfig
```
- [ ] How to copy a file or dir ?
```
cp <source> <destination>
```
- [ ] How to Install package in ubuntu ?
```
apt update
apt install <packagename>
```

- [ ] Check current directory you are working in
```
pwd
```
- [ ] How to download a file using wget
```
wget url
```
- [ ]  How to Install Tomcat
```
wget https://dlcdn.apache.org/tomcat/tomcat-9/v9.0.76/bin/apache-tomcat-9.0.76.tar.gz
```
- [ ]  Untar using below command

```
tar -xvf apache-tomcat-9.0.76.tar.gz
```
- [ ] Move to the Apache unzipped folder

```
 cd apache-tomcat-9.0.76
 ```
 - [ ]  Change the port number for Tomcat

```
vi conf/server.xml


Save this file 
```
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/5476fd3f-f6ba-4019-a1fd-e5dd7823342c)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/70c006f4-87cf-42d3-9eeb-4bd388e213c2)
- [ ] Start tomcat service 

```
./bin/startup.sh 
```
- [ ] Test Tomact Server

```
localhost:8090
```

- [ ]  Deploy Jenkins on Tomcat

```
cd webapps
```
- [ ] Download jenkins war file 

```
wget https://get.jenkins.io/war-stable/2.401.1/jenkins.war
```
- [ ] Open your jenkins 

```
localhost:8090/jenkins
```

### Now you can continue to set the password for your jenkins 

