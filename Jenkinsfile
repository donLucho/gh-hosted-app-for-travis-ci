pipeline {

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
        error "Fail blog... DOT ORG"
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

}

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