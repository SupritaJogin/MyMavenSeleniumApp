pipeline {
    agent any

    tools {
        jdk 'jdk24'       // Make sure 'jdk24' is configured in Jenkins under Global Tool Configuration
        maven 'Maven'     // Same for 'Maven'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SupritaJogin/YourSeleniumProject.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Report') {
            steps {
                // Optional: If using Surefire/Allure/Extent Reports
                echo 'Collecting and publishing test reports...'
            }
        }
    }

    post {
        success {
            echo 'Selenium tests passed successfully!'
        }
        failure {
            echo 'Selenium tests failed. Please check logs.'
        }
    }
}
