#!/usr/bin/env groovy
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
	bat 'echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"'      
      }
    }
    stage('SetMavenPath') {
      steps {
        bat 'set PATH=%PATH%;C:\\JDEV12R2V1SOA\\oracle_common\\modules\\org.apache.maven_3.2.5\\bin'
      }
    }
	stage('Approval') {
      steps {
	 script {     
	     def selectedDetails = input(
		id: 'userInput', message: 'Let\'s promote?', parameters: [
		[$class: 'ChoiceParameterDefinition', choices: 'DEV\nUAT\nPRD', description: 'Environment', name: 'env'],
		[$class: 'TextParameterDefinition', defaultValue: 'ChangeID', description: 'Change Request ID', name: 'change']
		])
	 echo ("Env: "+selectedDetails['env'])
	 echo ("ChangeID: "+selectedDetails['change'])  		 
	 }
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
		archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
      }
    }
  }
}
