pipeline {
    agent any

    tools {
        jdk 'java 17'
        maven 'maven3.6'
    }

    stages {
        stage('Compile') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package Application') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo '✅ Build and packaging completed successfully!'
        }
        failure {
            echo 'Build failed. Check the logs.'
        }
    }
}
