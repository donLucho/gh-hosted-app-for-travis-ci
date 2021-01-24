pipeline {

  agent any

  environment {
    
    GIMME_DERRP = '1'
    // GIMME_DERRP = '0'

  }

  stages {

    stage("error"){
      when {
        expression { GIMME_DERRP == '1' }
      }
      steps {
        echo "Aw, man! You broke it!"
        error "The test has failed. TRY AGAIN!"
      }
    }
    
    stage("build") {
      when {
        expression { GIMME_DERRP == '0' }
      }
      steps {
        echo "Building the application..."
        
        nodejs("Node-14.15.4") {
          sh "node --version"
          sh "yarn --version"
          // sh "npm install"
          // sh "yarn"
        }

      }
    }

    stage("test") {
      when {
        expression { GIMME_DERRP == '0' }
      }
      steps {
        echo "Testing the application..."
        
        nodejs("Node-14.15.4") {
          sh "node --version"
          sh "yarn --version"
          // sh "npm test"
          // sh "yarn run test"
        }

      }
      
    }
    
  }

  post {
    always {
      echo "All of your stages have completed..."
      // emailext attachLog: true, body: '$DEFAULT_CONTENT', compressLog: true, subject: '$DEFAULT_SUBJECT', to: '$DEFAULT_RECIPIENTS'
      emailext body: '$DEFAULT_CONTENT', subject: '$DEFAULT_SUBJECT', to: '$DEFAULT_RECIPIENTS'
    }
    success {  
      echo "Plus, all of your stages have succeeded..."
    }
    failure {
      echo "But one or more of your stages have failed..."
    }
  }

}