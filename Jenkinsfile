pipeline {
    agent any 
    tools {
	nodejs 'Node_20'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'npm install'
                sh 'npm run build'
            }
            post {
                success {
                    echo 'Build succeeded!'
                }
                failure {
                    echo 'Build failed!'
                }
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'npm test' 
            }
            post {
                success {
                    echo 'All tests passed!'
                }
                failure {
                    echo 'Some tests failed!'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'docker-compose up -d'
            }
            post {
                success {
                    echo 'Deploy succeeded!'
                }
                failure {
                    echo 'Deploy failed!'
                }
            }
        }
    }
}
