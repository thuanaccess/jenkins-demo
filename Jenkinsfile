pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                bat 'python3 helloworld.py'          
		  }
        }
        
    }
}