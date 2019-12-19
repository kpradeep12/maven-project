pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
		sh 'export M2_HOME=/Users/pradeep/.sdkman/candidates/maven/3.6.0'
		sh 'export PATH=$PATH:$M2_HOME/bin'
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
