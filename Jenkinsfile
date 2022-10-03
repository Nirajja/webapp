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
            stage ('Depoly-on-crm-test') {
               
               steps {
                   sh 'scp /home/ec2-user/webapp/target/*.war crm-test@10.0.2.105:/home/ec2-user/testwar'
                }
            
            }

        }
}		
