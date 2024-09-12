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
          configName: "target",
          transfers: [
		  sshTransfer(
		  sourceFiles: 'build/libs/ROOT.war'
		  remoteDirectory: '/home/loo/tomcat/apache-tomcat-9.0.94/webapps/')
		  ],
          verbose: true
        )
      ]
    )
   }
        }
    }
}