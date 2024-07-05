pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:20-alpine'
                    reuseNode true
                }
            }
            steps {
                script {
                    sh '''
                        echo 'Building'
                        ls -la
                        node --version
                        npm --version
                        npm install
                        ls -la
                    '''
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Testing...'
                    sh 'npm test'
                }
            }
        }
    }
}
