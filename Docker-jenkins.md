- [ ] Login to Jenkins and Install docker plugins
- 
**Step 1** : Head over to Jenkins Dashboard –> Manage Jenkins –> Manage Plugins. 
**Step 2:** Under the Available tab, search for “Docker” and install the docker cloud plugin and restart Jenkins.

- [ ] Go to  Dashboard- > Manage Jenkins -> Configure System -> Docker Slaves

![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/ce50f3c7-715c-488b-a4b1-ffb9fa255636)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/1d79acee-d8fe-4bc7-b47f-9e8b5465e02e)
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/147b2974-4a49-476e-b0c5-8046f5c78bec)



## NOTES
- You should have docker installed 
- User should have permission for docker commands
- [ ]  On Linux set the permission

```
chmod 777 /var/run/docker.sock
```

- [ ] Jenkinsfile example
```
pipeline {
    agent { docker { image 'maven:3.3.3' } }
      stages {
        stage('log version info') {
          steps {
            sh 'mvn --version'
            sh 'mvn clean install'
      }
    }
 }
}
```
