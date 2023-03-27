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
		echo "Building1.."
		echo "Building123.."
                python3 helloworld.py
			'''          
		  }
        }
	       
       
    }
}
