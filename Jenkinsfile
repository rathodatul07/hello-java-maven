pipeline {
    agent any

    tools {
        maven 'Maven 3.x'
        jdk 'Java 17'
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building application'
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests'
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging application'
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application (demo)'
                sh 'cp target/*.jar /tmp/'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully'
        }
        failure {
            echo 'CI/CD Pipeline failed'
        }
    }
}

