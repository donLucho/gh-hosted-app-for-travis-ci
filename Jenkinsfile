pipeline {
  
  agent any

  tools {
    gradle 'Gradle'
  }

  stages {
    
    stage("run frontend with npm") {
      steps {
        echo 'executing npm...'
        // wrapper('name-of-installation') {}
        nodejs('Node-14.15.4') {
          sh 'node --version'
          sh 'npm --version'
          // sh 'npm install'
          // sh 'npm run build'
        }
      }
    }

    stage("run backend with gradle") {
      steps {
        echo 'executing gradle...'
        withGradle() {
          // sh 'gradle wrapper'
          sh './gradlew --version'
        }
      }
    }
    
  }

}
