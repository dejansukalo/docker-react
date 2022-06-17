pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dejansukalo-dockerhub')
    }
    stages {
        stage ('Build'){
            steps {
                sh 'docker build -t dejansukalo/myreactapp:latest .'
            }
        }
    }
        stage ('Login'){
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --pasword-stdin'
            }
        }
        stage ('Push') {
            steps {
                sh 'docker push dejansukalo/myreactapp:latest'
            }
        }
    }
