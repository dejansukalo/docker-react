pipeline {
    agent { 
        docker {
            filename 'Dockerfile.dev'
        }
    }
    stages {
        stage('Test') {
            steps {
            sh 'npm run test'
      }
    }
  }
}
