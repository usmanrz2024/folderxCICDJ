
pipeline {
    agent {
    docker {
            image 'node:6-alpine'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Build'){
            steps {
                script{
                    sh 'npm install'
                }
            }
        }
        stage('Test'){
            steps{
                script {
                    sh 'npm test || echo "No tests configured"'

                }
            }
        }
        stage('Deploy'){
            steps{
                script{
                    sh 'echo "Deploying the applications"'
                    sh 'node index.js'
                }
            }
        }
    }
}