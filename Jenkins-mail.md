- [ ] Login to https://support.google.com/accounts
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/0c795a50-cd04-4f28-9abb-0f82bf4febce)
- [ ] Search for Sign in with app passwords
![image](https://github.com/Ramkhushi/Learning-notes/assets/120269399/78e1c44e-a8df-4a87-a078-967e9b391c61)

- [ ] Follow all the steps from the link itself

- [ ] COnfigure Email notification with jenkins

 - [ ] Log in to your Jenkins instance and navigate to “Manage Jenkins” > “Configure System.”
```
  http://your_ip:8080/manage/configure
```
- [ ] Scroll down to the “Extended E-mail Notification” section.

- [ ]  Enter the following SMTP settings:
```
    SMTP server: smtp.gmail.com
    Default user e-mail suffix: @gmail.com (replace with your own domain if using Google Workspace)
    Use SMTP Authentication: Yes
    User Name: Your full Gmail email address
    Password: Your 16 digit app passowrd which you ahve genrated above
  Click “Advanced” and check “Use SSL.”
  Set the SMTP Port to 465.
  Save the configuration.
  ```
  
  - [ ] Creating a Jenkins Pipeline to Send Emails

```
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Your build steps here
            }
        }
    }
    post {
        success {
            emailext (
                to: 'your@email.com',
                subject: "SUCCESS: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: "The job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' completed successfully."
            )
        }
        failure {
            emailext (
                to: 'your@email.com',
                subject: "FAILURE: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]'",
                body: "The job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' failed."
            )
        }
    }
}
```
