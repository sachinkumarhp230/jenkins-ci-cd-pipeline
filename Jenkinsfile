pipeline {

  agent any
	
    stages {
	
	  stage ('Checkout'){
	    
		steps{
		
		  git branch: 'main',
		  
		    url: 'https://github.com/sachinkumarhp230/jenkins-ci-cd-pipeline.git' 
		}
	  }
	  
	  
	  stage ('Build'){
	  
	    steps{
		
		  echo "No build is required for the static website" 
		}
	  }
	  
	  
	  stage ('Test'){
	    
		steps{
		
		  sh 'test -f index.html'
		}
	  }
	  
	  
	  stage ('Deploy'){
	  
	    steps{
		
		  sh '''
		  scp -o StrictHostKeyChecking=no index.html ubuntu@172.31.23.46:/var/www/html/
		  '''
		}
	  }
	}
	
	
	post {
        success {
            echo "Deployment Successful 🚀"
        }
        failure {
            echo "Deployment Failed ❌"
        }
    }
}
