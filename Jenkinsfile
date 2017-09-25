pipeline {
  agent any
  stages {
    stage('Initialization') {
      steps {
        parallel(
          "Building": {
            sh '''date 
echo "ledger job triggering to build"'''
            
          },
          "Developing": {
            sh '''date 
echo "Successfully triggering the ledger build"'''
            
          },
          "Initialization": {
            sh '''date
echo "trigger job is completed successfully"'''
            
          },
          "Staging ": {
            sleep 10
            
          }
        )
      }
    }
    stage('Deploying') {
      steps {
        git(url: 'https://github.com/kvootla/ledger.git', branch: 'ledger-78752', changelog: true)
      }
    }
  }
}