pipeline {
    agent any 
	
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

        stage ('Echo Branch') {
    
            steps {

                   echo "This is master branch"
			    }
			
	    }

        stage ('Create Images') {

            steps {

                   sh 'docker build -t tomcatimg .'
                }

        }

        stage ('Create and Run Container') {

            steps {
      
                   sh 'docker run -itd -v /jenkins-data/maven-data/webapp/target:/usr/local/tomcat/webapps -p 8090:8080 --name server1 tomcatimg'  
			    }
				   
		}

	}
}	
