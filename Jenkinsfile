pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('Deploy') {
      steps {
        archiveArtifacts '*.sar'
      }
    }
  }
}