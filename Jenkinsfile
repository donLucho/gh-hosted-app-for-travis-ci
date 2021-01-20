pipeline {
  
  // agent {
  //   docker {
  //     image 'node:14-alpine'
  //     args '-p 3000:3000'
  //   }
  // }

  agent any

  stages {
    
    stage("build") {
      steps {
        echo "Building the application..."
        // sh "npm install"
        sh "yarn"
      }
    }

    stage("test") {
      
      steps {
        echo "Testing the application..."
        // sh "npm test"
        sh "yarn run test"
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
      }
    }

    stage("test") {
      
      steps {
        echo "Testing the application..."
      }
      
    }
    
  }

} */