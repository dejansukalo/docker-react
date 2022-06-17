pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dejansukalo-dockerhub')
    }
    stages {
        stage ('Build') {
            steps {
                sh 'docker build -t dejansukalo/myreactapp:latest .'
            }
        }
        stage ('Login') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage ('Push') {
            steps {
                sh 'docker push dejansukalo/myreactapp:latest'
            }
        }
        stage ('Run container on Dev server') {
            sshagent(['dev-server']) {
                sh "ssh -o StrictHostKeyChecking=no ec2-user@3.67.224.128 docker run -p 8080:8080 -d --name my-app dejansukalo/myreactapp:latest"
            }
        }
    }
}