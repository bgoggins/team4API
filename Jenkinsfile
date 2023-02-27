node {
    stage ("Checkout React Client"){
        git branch: 'main', url: 'https://github.com/bgoggins/team4ReactFrontend.git'
    }
    
    stage ("npm install - React Client") {
	
        sh 'npm install'

    }
    
    stage ("npm audit - React Client") {
        sh 'npm audit fix --force || true' 
    }
    
    stage('User Acceptance Test - React Client') {
	
	  def response= input message: 'Is this build good to go?',
	   parameters: [choice(choices: 'Yes\nNo', 
	   description: '', name: 'Pass')]
	
	  if(response=="Yes") {

	    stage('Release- React Client') {
	     sh 'echo Frontend React Client is ready to release!'
	    }
	  }
    }
    
    stage ("Launch - React Client") {
       sh 'npm start'
    }
}
