pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/DeekshaHarish12/MyMavenPracticeAutomation.git'
            }
        }

        stage('Build & Test') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Show Build Output') {
            steps {
                sh 'ls -l target'
            }
        }

        stage('Run Application') {
            steps {
                sh 'java -cp target/MyMavenPracticeAutomationApp-1.0-SNAPSHOT.jar com.example.App'
            }
        }
    }

    post {
        success {
            echo 'Build and execution successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
