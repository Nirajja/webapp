pipeline {
    agent {
	  "node" {
	   "lebel" 'built-in' 
	customWorkspace '/mnt/jenkins/webapp'
	}
}
	stages {
	    stage ('Compile Stage') {
		
		    steps {
			
			       sh 'mvn clean compile'
				}
		}

		stage ('Testing Stage') {
		
		    steps {
			
			       sh 'mvn test'
				}
		}

		stage ('Install Stage') {
		    steps {
			
			       sh 'mvn install'
				}
			}
	}
}
