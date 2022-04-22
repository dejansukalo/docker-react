pipeline {
    agent any {
        dockerfile true
    }
    stages {
        stage ('Test'){
            steps {
                sh 'npm run test'
            }
        }
    }
}
