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
                sh 'mvn clean test'
            }
        }
    }

    post {
        always {
            junit '**/target/surefire-reports/*.xml'
        }

        success {
            echo 'Build and Selenium tests successful!'
        }

        failure {
            echo 'Build or tests failed!'
        }
    }
}
