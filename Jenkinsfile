pipeline {
    agent { label 'agent' }

    stages {
        stage('git scm update') {
            steps {
                git url: 'https://github.com/manuma159159/nodejs-app.git', branch: 'main'
            }
        }
        stage('docker build & deploy') {
            steps {
		sh 'IMAGE_NAME=manuma159159/nodejsapp docker compose build'
            }
        }
	stage('docker hub push') {
            steps {
                sh '''
 		   docker login -u manuma159159 -p rlatjddmsdmlrnrmf123!@#
                   docker push manuma159159/nodejsapp
		'''
            }
        }
	stage('microk8s run pod') {
            steps {
                sh ' microk8s kubectl run app1 --image=manuma159159/nodejsapp '
            }
        }
    }
}
