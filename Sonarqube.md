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
cd sonarqube-9.5.0.56709
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
