pipeline {
  agent any
  stages {
    stage('Initialization') {
      steps {
        parallel(
          "Initialization": {
            sh '''date 
echo "graylog job triggering to build"'''
            
          },
          "Building": {
            sh '''date 
echo "Successfully triggering the graylog build"'''
            
          }
        )
      }
    }
  }
}