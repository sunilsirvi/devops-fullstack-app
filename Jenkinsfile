pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }

        stage('build images') {
            steps {
                sh 'docker-compose build'
            }
        }

        stage('deploy application') {
            steps {
                sh 'docker-compose.yaml up -d'
            }
        }
    }

    post {
        success {
            echo 'application deployed successfully'
        }

        failure {
            echo 'pipeline failed'
        }
    }
}
