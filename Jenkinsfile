pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Test'
            }
        }
        stage('Build') {
            steps {
                bat 'gradlew.bat clean build'
            }
        }
        stage('Deploy') {
  steps {
    scp binary/lib/ROOT.war target
   }
        }
    }
}