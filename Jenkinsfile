pipeline {
    agent any

    stages {
        stage('git scm update') {
            steps {
                git url: 'https://github.com/manuma159159/nodejs-app.git', branch: 'main'
            }
        }
        stage('docker build & deploy') {
            steps {
      				sh '''
      				docker compose up --build -d
              '''
            }	
        }
    }
}

# 여기서 git url : '내 깃허브 nodejs-app 주소' 이다.
