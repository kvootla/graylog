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
          "Developing": {
            sleep 10
          },
          "Integrating": {
            sleep 30
            
          "Staging ": {
            sleep 10
          }
        )
      }
    }
    stage('Deploying') {
      steps {
        parallel(
          "Deploying": {
            git(url: 'https://github.com/kvootla/ledger.git', branch: 'ledger-78751', changelog: true)
            
          },
          "Staging": {
            sleep 30
            
          },
          "Developing": {
            sleep 10
            
          },
          "Integrating": {
            sleep 30
            
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
            
          },
          "Auto-Tested": {
            sh '''date
echo "auto test job completed successfully" '''
            
          }
        )
      }
    }
    stage('Release') {
      steps {
        parallel(
          "Release": {
            sh '''date
echo "Release job is completed successfully"'''
            
          },
          "Staging ": {
            sh '''date
echo "code getting to staging for further release" '''
            
          }
        )
      }
    }
  }
}
