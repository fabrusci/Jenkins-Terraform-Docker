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
        sh '''echo "pluto"'''
        withCredentials([sshUserPrivateKey(credentialsId: 'TEST-Envi', keyFileVariable: 'SSH_KEY')]) {
            // Inside this block, SSH_KEY variable is available
            echo "SSH Key: $SSH_KEY"

            // Use the private key for some operation (e.g., connecting to a remote server)
            sh 'ssh -i $SSH_KEY user@remote-server "echo Hello, world!"'
          }
      }
    }

    stage('MyStage') {
      steps {
      sh 'env'
      }
    }

  }
}
