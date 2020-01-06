pipeline { 
    agent any
    stages { 
        stage('Build') { 
            steps { 
               echo 'Building the app'
			   sh 'mvn clean install'
            }
        }
		stage('Sonarqube') {
			environment {
				scannerHome = tool 'SonarQubeScanner'
			}
			steps {
				withSonarQubeEnv('sonarqube') {
					sh "${scannerHome}/bin/sonar-scanner"
				}
				timeout(time: 10, unit: 'MINUTES') {
					waitForQualityGate abortPipeline: true
				}
			}
		}
    }
}
