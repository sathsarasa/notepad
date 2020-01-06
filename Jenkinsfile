pipeline { 
    agent any
    stages { 
        stage('Build') { 
            steps { 
               echo 'Building the app'
			   sh 'mvn clean install'
            }
        }
		stage('SonarQube analysis') { 
			environment {
				scannerHome = tool 'sonarqube'
			}
			steps {
			  sh 'mvn sonar:sonar ' + 
			  '-Dsonar.projectKey=notebook-app ' +
			  '-Dsonar.host.url=http://34.73.81.112:9000 ' +
			  '-Dsonar.login=36e23f7213f4c52990ae21eec7adef4cfe831dd1'			
			}
		}
    }
}
