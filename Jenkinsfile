pipeline {
    agent any
    tools {
	maven 'localMaven'
    }
    stages {
        stage('Build') {
            steps {
		sh 'mvn --version'
                sh 'mvn clean package'
            }
	   post {
	     success {
			echo 'Now archiving'
			archiveArtifacts artifacts: '**/target/*.war'
		}
           }
        }
    }
}
