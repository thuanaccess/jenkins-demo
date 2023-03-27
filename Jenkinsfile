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
	       
        stage('Hello') {
            steps {
                sh "echo 'Hello world,1' >> test.csv"
                    }
		post {
           	 always{
                archiveArtifacts artifacts: '*.csv', onlyIfSuccessful: true
                
                emailext to: "mavanthuan05051998@gmail.com",
                subject: "jenkins build:${currentBuild.currentResult}: ${env.JOB_NAME}",
                body: "${currentBuild.currentResult}: Job ${env.JOB_NAME}\nMore Info can be found here: ${env.BUILD_URL}",
                attachmentsPattern: '*.csv'
                
            cleanWs()
            }
        }
            }
    
    
        
    }
}
