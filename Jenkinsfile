pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
			sh'''
                echo "Building.."
                python3 helloworld.py
			'''          
		  }
        }
	       
       
    }
}
