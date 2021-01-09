pipeline {
  agent any
  stages {
    stage('Buzz Test') {
      steps {
        sh './jenkins/test-all.sh'
        junit '**/data/*.xml'
      }
    }

    stage('archiveArtifacts') {
      steps {
        archiveArtifacts(fingerprint: true, artifacts: '/jenkins/data/*.xml')
      }
    }

  }
}