pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('Deploy') {
      steps {
        dir(path: 'SOA12cPOCApp') {
          bat 'mvn pre-integration-test'
        }
        
      }
    }
  }
}