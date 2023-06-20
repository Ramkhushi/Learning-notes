- [ ] Pipeline one example
```
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
```
- [ ] Multi Command Pipeline


```
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                
                sh '''
                      ls
                      date
                   '''
            }
        }
    }
}
```
- [ ] Multiple stage pipeline 
```
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Stage2') {
            steps {
                echo "stage2"
            }
        }
    }
}

```






- [ ] Parameterized Build Example
```
pipeline {
    agent any
    parameters {
      string defaultValue: ' ', name: 'env'
}

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}

```

- [ ] Scheduled pipeline
```
https://www.jenkins.io/doc/book/pipeline/syntax/#parameters
pipeline {
    agent any
    triggers {
        cron('H */4 * * 1-5')
    }
    stages {
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
```


- [ ] Pipeline with tools

```
https://www.jenkins.io/doc/book/pipeline/syntax/#parameters
pipeline {
    agent any
    tools {
        maven 'apache-maven-3.0.1'
    }
    stages {
        stage('Example') {
            steps {
                sh 'mvn --version'
            }
        }
    }
}
```



- [ ] When condition 
```
https://www.jenkins.io/doc/book/pipeline/syntax/#parameters
pipeline {
    agent any
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Example Deploy') {
            when {
                branch 'production'
            }
            steps {
                echo 'Deploying'
            }
        }
    }
}
```


- [ ] Jenkinsfile for Enviroinment variable
```
pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }
    }
}
```

- [ ] Set Environmenr Variable
```
pipeline {
    agent any
    environment {
        CC = 'clang'
    }
    stages {
        stage('Example') {
            environment {
                DEBUG_FLAGS = '-g'
            }
            steps {
                sh 'printenv'
            }
        }
    }
}
```

- [ ] Parameter Build
```
pipeline {
  agent any
  parameters {
    string(name: 'STATEMENT', defaultValue: 'hello; ls /', description: 'What should I say?')
  }
  stages {
    stage('Example') {
      steps {
        /* WRONG! */
        sh("echo ${STATEMENT}")
      }
    }
  }
}
```

- [ ] Jenkins Pipeline on multiple agents
```
pipeline {
    agent none
    stages {
        stage('Build') {
            agent any
            steps {
                checkout scm
                sh 'make'
                stash includes: '**/target/*.jar', name: 'app'
            }
        }
        stage('Test on Linux') {
            agent {
                label 'linux'
            }
            steps {
                unstash 'app'
                sh 'make check'
            }
            post {
                always {
                    junit '**/target/*.xml'
                }
            }
        }
        stage('Test on Windows') {
            agent {
                label 'windows'
            }
            steps {
                unstash 'app'
                bat 'make check'
            }
            post {
                always {
                    junit '**/target/*.xml'
                }
            }
        }
    }
}
```


- [ ] Check below for more details
```
pipeline {
    agent any
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 1, unit: 'SECONDS')
    }
    stages {
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
```


- [ ] Pipeline which requires you to provide input

```
pipeline {
    agent any
    stages {
        stage('Echo') {
            input { 
                message "Do you want to salute?" 
            }
            steps {
                echo "Hello!"
            }
        }
    }
}
```

- [ ] Pipeline for When condition

```
pipeline {
    agent any
    stages {
        stage('Echo') {
            when { 
                expression { env.GIT_BRANCH == 'origin/main' } 
            }
            steps {
                echo 'Hello from the main branch!'
            }
        }
    }
```

- [ ] Pipeline with Global variable
```
pipeline {
    agent any
    environment { PERSON = 'Joel'}
    stages {
        stage('Hello') {
            steps {
                echo "Hello ${PERSON}"
            }
        }
    }
}
```

- [ ] Pipeline for per stage environment variables
```
pipeline {
    agent any
    stages {
        stage('Hello') {
            environment { PERSON = 'Aykut'} 
            steps {
                echo "Hello ${PERSON}" 
            }
        }
        stage('Bye') {
            steps {
                echo "Bye ${PERSON}" 
            }
        }
    }
}
```
