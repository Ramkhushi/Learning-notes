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
                echo 'Hello World'
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

- [ ] Build with env variable
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

