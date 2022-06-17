pipeline {
    agent {
        dockerfile true
    }
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
}
