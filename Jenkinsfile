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

        stage('Run Selenium Test') {
            steps {
                sh '''
                echo "Listing target folder..."
                ls -l target

                echo "Running Selenium Test..."
                java -cp target/MyMavenPracticeAutomationApp-1.0-SNAPSHOT.jar com.example.App
                '''
            }
        }
    }

    post {
        success {
            echo 'Build and Selenium test successful!'
        }
        failure {
            echo 'Build or test failed!'
        }
    }
}
