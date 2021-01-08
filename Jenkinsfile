pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        sh './jenkins/build.sh'
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