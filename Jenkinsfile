pipeline {
agent any

```
stages {

    stage('Clone Repository') {
        steps {
            git 'https://github.com/Shailendra336/devops_shailendra.git'
        }
    }

    stage('Check Workspace Files') {
        steps {
            sh 'ls -ltrh'
        }
    }

    stage('Run Server Details Script') {
        steps {
            sh '''
            chmod +x server_details
            ./server_details | tee server_report.txt
            '''
        }
    }

    stage('Archive Report') {
        steps {
            archiveArtifacts artifacts: 'server_report.txt', fingerprint: true
        }
    }

}
```

}
