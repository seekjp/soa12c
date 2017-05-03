#!groovy
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
        input(
			 id: 'userInput', message: 'Let\'s promote?', parameters: [
			 [$class: 'TextParameterDefinition', defaultValue: 'Dev', description: 'Environment', name: 'env'],
			 [$class: 'TextParameterDefinition', defaultValue: 'ChangeID', description: 'Change Request ID', name: 'change']
			])
			echo ("Env: "+userInput['env'])
			echo ("ChangeID: "+userInput['change'])
      }
    }
	stage('Deploy') {
      steps {
        dir(path: 'SOA12cPOCApp') {
          bat 'mvn pre-integration-test'
        }
      }
    }
	stage('PushArtifacts') {
      steps {
		archiveArtifacts '**/target/*.jar'
      }
    }
  }
}
