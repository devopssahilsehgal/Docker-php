pipeline {
  agent {
    docker {
      image 'bzzzcentos:7'
    }

  }
  stages {
    stage('Buzz Test') {
      parallel {
        stage('Buzz Test') {
          steps {
            echo "I am a ${BUZZ_NAME}"
            sh './jenkins/test-all.sh'
            junit '**/jenkins/data/*.xml'
          }
        }

        stage('Testing B') {
          steps {
            sh '''sleep 10
echo done.'''
          }
        }

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