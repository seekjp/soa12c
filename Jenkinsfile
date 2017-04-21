pipeline {
  agent {
    node {
      label 'master'
    }    
  }
  stages {
    stage('Initialize') {
      steps {
        bat 'echo "SOA 12c Deploy!"'
      }
    }
    stage('SetMavenPath') {
      steps {
        bat 'set PATH=%PATH%;C:\\JDEV12R2V1SOA\\oracle_common\\modules\\org.apache.maven_3.2.5\\bin'
      }
    }
	stage('Approval') {
      steps {
        input 'Good to go?'
      }
    }
	stage('Deploy') {
      steps {
        bat 'cd SOA12cPOCApp'
      }		
      steps {
        bat 'mvn pre-integration-test'
      }
    }	
  }
}
