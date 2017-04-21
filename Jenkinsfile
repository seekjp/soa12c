pipeline {
  agent {
    node {
      label 'master'
    }
    
  }
  stages {
    stage('Initialize') {
      steps {
        bat 'echo "Hello Jp!"'
      }
    stage('SetMavenPath') {
      steps {
        bat '%PATH%;C:\JDEV12R2V1SOA\oracle_common\modules\org.apache.maven_3.2.5\bin'
      }      
    }
  }
}
