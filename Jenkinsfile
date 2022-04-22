pipeline {
    agent none
    stage ('Test') {
        agent {
            dockerfile {
            filename 'Dockerfile.dev'
            }
            steps {
            sh 'npm run test'
            }
        }
    }
}
