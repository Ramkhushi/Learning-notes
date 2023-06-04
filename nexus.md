## Nexus 
- [ ] Login to your Linux server and update the yum packages. Also install required utilities.
```
sudo yum update -y
sudo yum install wget -y
```
- [ ] Install OpenJDK 1.8

```
sudo yum install java-1.8.0-openjdk.x86_64 -y
```
- [ ] Create a directory named app and cd into the directory.
```
sudo mkdir /app && cd /app
```
- [ ]  Download the latest nexus. You can get the latest download links fo for nexus 

```
sudo wget -O nexus.tar.gz https://download.sonatype.com/nexus/3/latest-unix.tar.gz
```
- [ ] Untar the downloaded file.
```
sudo tar -xvf nexus.tar.gz
```
- [ ]  Rename the untared file to nexus.

```
sudo mv nexus-3* nexus
```
- [ ] create a new user named nexus to run the nexus service.

```
sudo adduser nexus
```
- [ ] Change the ownership of nexus files and nexus data directory to nexus user.

```
sudo chown -R nexus:nexus /app/nexus
sudo chown -R nexus:nexus /app/sonatype-work
```
- [ ] Open /app/nexus/bin/nexus.rc file
```
sudo vi  /app/nexus/bin/nexus.rc
run_as_user="nexus"
```
- [ ] Create a svc for nexus

```
sudo vi /etc/systemd/system/nexus.service
[Unit]
Description=nexus service
After=network.target

[Service]
Type=forking
LimitNOFILE=65536
User=nexus
Group=nexus
ExecStart=/app/nexus/bin/nexus start
ExecStop=/app/nexus/bin/nexus stop
User=nexus
Restart=on-abort

[Install]
WantedBy=multi-user.target
```

- [ ] Manage Nexus Service

```
sudo chkconfig nexus on

sudo systemctl start nexus

```
- [ ] Access nexus using ip:8081

```
localhost:8081
```
- [ ] Default username and password location will be given there

```
admin 
```




#### How to Create Nexus Repo
- [ ] Login to Nexus using admin user and password

- [ ] Click on Server Administrations and configuration

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/8fa250ce-e5bd-4091-8cd9-563d1abbbdd3)
- [ ] Click on Repositories

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/2adb1083-1bed-44ef-bf47-2a1aee4127e9)

- [ ] Click on create repository

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/a99d3932-d839-495d-a97f-e064f1eddbfe)
- [ ] Select maven 2 hosted

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/a3b6415b-e014-43ae-be03-1de2d8b2d163)

- [ ] Give any name and click on select

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/eee26426-b544-412e-a091-2514c9ac22ba)
- [ ] You will see on newly created repo

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/87cb17af-6106-4fbe-b345-d2e0a0b1f018)




## Jenkins and Nexus
- [ ] Login to Jenkins and install the plugin

```
nexus platform
```
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/6af1a48a-7b7e-4d7e-8f2c-73a516e41311)

- [ ]  Configure nexus Server

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/5a91e4fe-f7c8-417e-827d-03eabe902a5d)
- [ ] Click on system config
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/5ba311be-8e9d-45d7-85bb-8cf5eec6361b)

- [ ] Select Nexus server

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/0a1da1a2-9c3d-4412-9650-11e3bcc74acc)

- [ ] Fill the information below
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/5d53e84c-199a-4a9c-aa53-7d3ff4e9d52d)



