
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Verify Artifact') {
            steps {
                sh 'ls -lh target/*.war'
            }
        }
    }

    post {
        success {
            echo 'Life Insurance WAR artifact created successfully!'
        }
        failure {
            echo 'Build failed. Check Console Output.'
        }
    }
}

