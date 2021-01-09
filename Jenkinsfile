pipeline {
  agent any
  stages {
    stage('Buzz Test') {
      steps {
        echo "I am a ${BUZZ_NAME}"
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
  environment {
    BUZZ_NAME = 'Worker bee'
  }
}