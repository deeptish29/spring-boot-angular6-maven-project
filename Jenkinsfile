pipeline {
    agent any
	 
    stages {
        stage('CodeCheckOut') {
            steps {
                script {
                    checkout scm
			
		}
	    }
	}
	    stage('Build') {
		    steps {
			    script{
		    try {
			    echo 'get maven version'
			 sh " wget http://www-us.apache.org/dist/maven/maven-3/3.1.1/binaries/apache-maven-3.1.1-bin.zip"
			sh "unzip -o apache-maven-3.1.1-bin.zip"
			    sh "pwd"
			sh "ls -l"
			
			   
				    env.M2_HOME="/home/centos/apache-maven-3.1.1"
				    env.MAVEN_HOME="/home/centos/apache-maven-3.1.1"
			            env.PATH="$PATH:$M2_HOME/bin"
			    sh "echo $M2_HOME"
			    
			    
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
