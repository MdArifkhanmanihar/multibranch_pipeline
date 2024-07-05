pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:20.9.0-alpine'
                    reuseNode true
                }
            }
            steps {
                script {
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
        }

        stage('Test') {
            steps {
                script {
                    echo 'Testing...'
                }
            }
        }
    }
}
