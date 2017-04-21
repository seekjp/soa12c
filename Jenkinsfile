pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('Deploy') {
      steps {
        dir(path: 'cd SOA12cPOCApp') {
          bat 'mvn pre-integration-test'
        }
        
      }
    }
  }
}