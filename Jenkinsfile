pipeline {
    agent any
	 
    stages {
        stage('CodeCheckOut') {
            steps {
                script {
                    checkout scm
			def mvnHome = tool 'MAVEN_3.1'
			
		}
	    }
	}
	    stage('Build') {
		    steps {
			    script{
				     checkout scm
		    try {
			    
			    def mvnHome = tool 'MAVEN_3.1'
		
			    
                        sh "mvn clean install"
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
