pipeline {
  agent {
    node {
      label 'soa12clab'
    }
    
  }
  stages {
    stage('Initilize') {
      steps {
        sh 'cd /opt/jenkins/agent/workspace/SOA12cPOC'
      }
    }
    stage('Deploy') {
      steps {
        sh '/opt/oracle/middleware/oracle_common/modules/org.apache.maven_3.2.5/bin/mvn pre-integration-test'
      }
    }
  }
}