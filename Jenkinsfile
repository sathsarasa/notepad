pipeline { 
    agent any
    stages { 
        stage('Build') { 
            steps { 
               echo 'Building the app'
			   sh 'mvn clean install'
            }
        }
    }
}
