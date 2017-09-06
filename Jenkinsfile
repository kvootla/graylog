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
            
          },
          "Staging ": {
            sh '''date
echo "trigger job is completed successfully"'''
            
          }
        )
      }
    }
    stage('Deploying') {
      steps {
        git(url: 'https://github.com/kvootla/graylog.git', branch: 'graylog-78381', changelog: true)
      }
    }
  }
}