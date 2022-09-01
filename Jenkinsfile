pipeline {
  agent {
    node {
      label 'nodejs'
    }
  }
  stages {
    stage ('Creating a new  application') {
      steps {
        sh 'oc new-app --name nexus quay.io/sravanipaladugu/nexus'
      }
    }
  }
  post {
    failure {
      echo 'FAILED'
      sh 'oc status'
    }
    success {
      sh 'oc expose service'
      sh 'oc status'
      sh 'oc get all'
      echo 'SUCCESS'
    }
  }
}
