node {
    
    stage ("Checkout React Client"){
        git branch: 'main', url: 'https://github.com/bgoggins/team4ReactFrontend.git'
    }
    
    stage ("Install dependencies - React Client") {
       sh 'npm install'
    }
    
    stage ("Containerize the app-docker build - react client") {
        sh 'docker build --rm -t team4-react:v1.1 .'
    }
    
    stage ("Inspect the docker image - react client"){
        sh "docker images team4-react:v1.1"
        sh "docker inspect team4-react:v1.1"
    }
    
    stage ("Run Docker container instance - react client"){
        sh "docker run -d --rm --name team4-react -p 3000:80 team4-react:v1.1"
    }
	 
	stage('User Acceptance Test - react client') {
	
	  def response= input message: 'Is this build good to go?',
	   parameters: [choice(choices: 'Yes\nNo', 
	   description: '', name: 'Pass')]
	
	  if(response=="Yes") {
	    stage('Release  - react client') {
	      sh "docker stop team4-react"
	      sh "echo MCC react client service is ready to release!"
	    }
	  }
    }
}