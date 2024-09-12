pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Test'
            }
        }
        stage('Build') {
            if (isUnix()) {
                sh './gradlew clean build'
            } else {
                bat 'gradlew.bat clean build'
            }
        }
    }
}