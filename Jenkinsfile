pipeline {

  agent any

  stages {	


	

	stage('Unit Test') {

	   steps {

			echo 'Project Testing stage'

			bat label: 'Test running', script: '''mvn test'''

	       

       		}

   	}

	  
	stage('Jacoco Coverage Report') {

        steps{

            jacoco()

		}

	}

	  

	stage('SonarQube'){

         steps{

            bat label: '', script: '''mvn sonar:sonar \

		 -Dsonar.host.url=http://localhost:9000 \

 		-Dsonar.login=8f0c6adb70b43372c63524783d8949f474f8acca'''

          }

      }

	  

	stage('Maven Package'){

		steps{

			echo 'Project packaging stage'

			bat label: 'Project packaging', script: '''mvn package'''

		}

	} 		

    

  }

}