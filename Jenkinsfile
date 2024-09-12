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
    sshPublisher(
      continueOnError: false,
      failOnError: true,
      publishers: [
        sshPublisherDesc(
          transfers: [sshTransfer(sourceFiles: 'build/libs/ROOT.war')],
          verbose: true
        )
      ]
    )
   }
        }
    }
}