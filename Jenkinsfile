pipeline {
  agent {
    docker {
      image 'node:20.10.0-alpine3.19'
    }

  }
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'node --version'
            sh '''echo "pippo"
'''
          }
        }

        stage('ppp') {
          steps {
            sh 'echo "ppp"'
          }
        }

      }
    }

    stage('MyStage') {
      steps {
        sh 'echo "MyStage"'
      }
    }

  }
}