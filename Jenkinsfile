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
		sshPublisher(publishers: [sshPublisherDesc(configName: 'target', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: 'tomcat/apache-tomcat-9.0.94/webapps/', remoteDirectorySDF: false, removePrefix: 'build/libs/', sourceFiles: 'build/libs/ROOT.war')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
		}
        }
    }
}
