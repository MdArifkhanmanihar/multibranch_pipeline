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
            agent{
                docker{
                    image 'node:20-alpine'
                    reuseNode true
                }
            }
            steps {
                script {
                    echo 'Testing dev branch for auto building and scanning...'
                    sh 'npm test'
                }
            }
        }
    }
}
