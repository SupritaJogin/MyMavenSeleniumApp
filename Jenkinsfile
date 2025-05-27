pipeline {
    agent any

    tools {
        jdk 'JDK'           // Change 'JDK' to your actual JDK name in Jenkins Global Tool Config
        maven 'Maven'       // Make sure Maven is configured under this name in Jenkins Global Tool Config
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SupritaJogin/MyMavenSeleniumApp.git', credentialsId: 'github-token'
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

           
