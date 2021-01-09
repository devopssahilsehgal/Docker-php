pipeline {
  agent any
  stages {
    stage('Buzz test') {
      steps {
        sh './jenkins/build.sh'
        junit(testResults: '**/data/*.xml', skipPublishingChecks: true)
      }
    }

    stage('Buzz Test') {
      steps {
        sh './jenkins/test-all.sh'
      }
    }

    stage('archiveArtifacts') {
      steps {
        archiveArtifacts(fingerprint: true, artifacts: '/jenkins/data/*.xml')
      }
    }

  }
}