pipeline {
    agent any

    tools {
        jdk 'JDK'     // This must match exactly the name you gave under Manage Jenkins > Tools > JDK
        maven 'Maven' // (if you added Maven tool by name 'Maven')
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SupritaJogin/MyMavenSeleniumApp.git'
            }
        }

        stage('Build') {
            steps {
                bat "mvn clean compile"
            }
        }

        stage('Test') {
            steps {
                bat "mvn test"
            }
        }

        stage('Report') {
            steps {
                echo "Tests completed. Check reports."
            }
        }
    }

    post {
        failure {
            echo "Selenium tests failed. Please check logs."
        }
    }
}
