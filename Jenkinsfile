pipeline {
    agent any
    stages {
        stage('CodeCheckOut') {
            steps {
                script {
                    checkout scm
                    def mvnHome = tool 'maven-3'
		    def JAVA_HOME  = tool 'JAVA_1.8'
		}
	    }
	}
	    stage('Build') {
		    steps {
			    script {	 
				    def JAVA_HOME  = tool 'JAVA_1.8'
                    checkout scm
                    def mvnHome = tool 'maven-3'
		    try {
                        sh "mvn clean install -U -Dmaven.test.skip=true"
                        currentBuild.result = 'SUCCESS'
                    } catch (Exception err) {
                        currentBuild.result = 'FAILURE'
                        sh "exit 1"
                    }
                }
            }
        }
    }   
}
