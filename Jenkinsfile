pipeline {
  
  agent {
    docker {
      image 'node:20.10.0-alpine3.19'
    }

  }
  stages {
    stage('build') {
      steps {
        sh 'node --version'
        sh '''echo "pippo"
'''
      }
    }

    stage('MyStage') {
      steps {
        sh 'echo $username'
      }
    }

  }
}
