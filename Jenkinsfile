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
            
          },
          "Developing": {
            sleep 10
            
          }
        )
      }
    }
    stage('Deploying') {
      steps {
        parallel(
          "Deploying": {
            git(url: 'https://github.com/kvootla/graylog.git', branch: 'graylog-78381', changelog: true)
            
          },
          "Staging": {
            sleep 30
            
          },
          "Developing": {
            sleep 10
            
          }
        )
      }
    }
    stage('Testing') {
      steps {
        parallel(
          "Testing": {
            sh '''date
echo "test job is completed successfully"'''
            
          },
          "Staging ": {
            sleep 10
            
          }
        )
      }
    }
    stage('Release') {
      steps {
        sh '''date
echo "Release job is completed successfully"'''
      }
    }
  }
}