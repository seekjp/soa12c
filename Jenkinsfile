pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('Approval') {
      steps {
        input 'Good to go?'
      }
    }
  }
}