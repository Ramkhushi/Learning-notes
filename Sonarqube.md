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
- [ ] Move to the repository

```
cd calcwebapp

mvn clean verify sonar:sonar \
  -Dsonar.projectKey=test-scan \
  -Dsonar.host.url=http://34.125.10.239:9000 \
  -Dsonar.login=sqp_c50250e9748708bb19ebd57141221ab7aec55dea
```

- [ ] Go back to your Sonarqube and check the data

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/e179488a-df67-4109-9e4f-60c28e95a042)



- [ ] Disable Authentication if you need to run this without creds
```
Go to sonarqube web page, then go to administration, after that go to security and disable " Force User Authentication".
````

 ## Sonarqube and Jenkins 
 - [ ] Install sonarqube plugin
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/e7105153-1178-4d17-8468-548974aec14e)


 - [ ] Create a token in Sonarqube  from administrator >Myaccount ->Security and generate a Global Token 
 - [ ] Create credentials for this token in jenkins

-  Go to Manage jenkins ->credentials
 ![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/f3ed57c6-f2f0-4cec-871a-e84a257f0911)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/9de91fc5-08e9-432f-b86e-f8bd97cf46f2)

 - [ ] Configure Sonarqube in jenkins 

- Go to -> Manage Jenkins -> System-> SonarQube servers 
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/3fb6dd29-669e-4c0b-8924-bb92796ea0cb)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/bc421a9b-f0aa-4ff8-a066-1e8bceb0efcc)

- [ ] Install Sonarqube Scanner 

-  Go to ->Manage Jenkins ->Tools- >SonarQube Scanner 
-  ![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/b1d9cd51-7fe7-4473-83ba-36c6997a4a3b)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/9449649c-0331-44ed-a938-26057201f7cf)


- [ ]  Create job in jenkins now

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/ae0ed0f6-2ebd-4e2b-9d2f-66035a850e90)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/33254072-045b-4cf9-af45-a582dce95f11)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/f422d146-2945-4c8d-a27a-4f479ca1e767)




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
