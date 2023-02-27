node {
    
    stage ("Checkout React Client"){
        git branch: 'main', url: ' https://github.com/foxwas/bah-mcc-react-day4.git'
    }
    
    stage ("Install dependencies - React Client") {
       sh 'npm install'
    }
    
    stage ("Launch - React Client") {
       sh 'npm start'
    }
}
    