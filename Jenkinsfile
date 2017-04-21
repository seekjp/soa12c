pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('Initialize') {
      steps {
        bat 'echo %WORKSPACE%'
      }
    }
  }
}