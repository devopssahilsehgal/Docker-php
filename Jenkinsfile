pipeline {
  agent any
  stages {
    stage('Buzz Test') {
      steps {
        sh './jenkins/test-all.sh'
        junit(testResults: './data/*.xml', skipPublishingChecks: true)
      }
    }

    stage('archiveArtifacts') {
      steps {
        archiveArtifacts(fingerprint: true, artifacts: '/jenkins/data/*.xml')
      }
    }

  }
}