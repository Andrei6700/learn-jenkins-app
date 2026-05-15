pipeline {
    agent any

    stages {
        // state build
        stage('Build') {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }

        // stage test
        stage('Test'){
            steps{
                echo 'Test stage'
            }
        }
    }
}
