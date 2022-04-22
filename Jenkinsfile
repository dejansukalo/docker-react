pipeline {
    agent any
    stages {
        stage ('Test') {
            dockerfile {
            filename 'Dockerfile.dev'
            }
            steps {
            sh 'npm run test'
            }
        }
    }
}
