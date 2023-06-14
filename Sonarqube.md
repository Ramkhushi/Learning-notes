### Sonarqube  Server Installation Steps on Linux 

- [ ] Install wget if this is not available
```
yum install wget -y
```
- [ ] Download the sonarqube software 
```
wget https://binaries.sonarsource.com/Distribution/sonarqube/sonarqube-9.5.0.56709.zip
```
- [ ] Install unzip command
```
yum install unzip -y
```
- [ ] unzip the newly downloaded software
```
unzip sonarqube-9.5.0.56709.zip
```
- [ ] Move to sonarqube dir
```
cd sonarqube-9.5.0.56709/bin/linux-x86-64
```
- [ ] Now java version 11 or later 
```
 yum install java-11-openjdk*
```

- [ ] Now start the sonarqube with standard user
```

 ./sonar.sh start
 ./sonar.sh status
```
  - [ ] Default user name and Password
```
admin
admin
```
- [ ] Default port number of Sonarqube
```
9000
```

- [ ] User Sonarqube with maven
- [ ] Create a token from administrator >Myaccount ->Security
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/819173b2-86df-44e5-865f-7b98c72f61d1)


- [ ] Create a project Manually to scan

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/20d8a4cb-d86d-44fe-ae2b-711a20e1be6c)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/d8f12bd8-3bbf-446a-b610-f5ebd5d78d5f)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/26fc0957-65d8-4571-a3db-07a71e3e0b3d)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/2c51173a-be9c-4c66-af27-000178f7718e)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/1fe53e02-f7c5-4ca9-bc87-6450e802c7f1)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/53c18537-6350-42b0-86c6-2374c0cfc3f0)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/86a74e94-9b41-447a-8d29-99f80574328a)

- [ ] Clone the repo

```
https://github.com/Ramkhushi/calcwebapp.git
```
- [ ] Copy the complete command and run this in your clone Repo


 ![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/157b4546-4ec8-40d8-9533-3c1717ad0305)



- [ ] Disable Authentication if you need to run this without creds
```
Go to sonarqube web page, then go to administration, after that go to security and disable " Force User Authentication".
````


------------------------------------
### Sonarqube Agent Configuration
- [ ] Download the sample code 
```
git clone https://github.com/monbostest/java-sonar-runner-simple
```

- [ ]  Download Sonaqube runner 
```
https://docs.sonarqube.org/latest/analysis/scan/sonarscanner/
https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.7.0.2747-linux.zip
```

 - [ ] Run sonarqube scanner against the code
```
/root/sonar-scanner-4.7.0.2747-linux/bin/sonar-scanner 
