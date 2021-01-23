pipeline {

  agent any

  environment {
    
    GIMME_DERRP = '1'
    //GIMME_DERRP = '0'

    // GIMME_DERRP = true
    // GIMME_DERRP = false

  }

  stages {

    stage("error"){
      when {
        // expression { GIMME_DERRP == true }
        expression { GIMME_DERRP == '1' }
      }
      steps {
        echo "Aw, man! You broke it!"
        error "The test has failed. TRY AGAIN!"
      }
    }
    
    stage("build") {
      when {
        // expression { GIMME_DERRP == false }
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
        // expression { GIMME_DERRP == false }
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
    }
    success {  
      echo "Plus, all of your stages have succeeded..."
    }
    failure {
      
      echo "But one or more of your stages have failed..."
      // emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'

      emailext body: 'One or more of your stages have failed', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Fail Test'
      
    }
  }

}

/* pipeline {

  agent any

  environment {
    GIMME_DERRP = true
    // GIMME_DERRP = false
  }

  stages {

    stage("error"){
      when {
        expression { GIMME_DERRP == true }
      }
      steps {
        echo "Aw, man! You broke it!"
        error "The test has failed. TRY AGAIN!"
      }
    }
    
    stage("build") {
      when {
        expression { GIMME_DERRP == false }
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
        expression { GIMME_DERRP == false }
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

} */

/* pipeline {

  agent any

  stages {
    
    stage("build") {
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

} */

/* pipeline {
  
  agent any

  stages {
    
    stage("build") {
      steps {
        echo "Building the application..."
      }
    }

    stage("test") {
      
      steps {
        echo "Testing the application..."
      }
      
    }
    
  }

} */