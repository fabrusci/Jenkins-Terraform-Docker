@Library('shared-library')_
pipeline {
  
  agent {
    /* docker {
      image 'node:20.10.0-alpine3.19'
    } */
    node { label 'agent1' }

  }

  stages {

     stage('Setup tools') {
      steps {
        sh (
          script: '''#!/bin/bash
                    asdf update
                 '''
        )
      }
    }

    stage('build') {
      steps {
        withCredentials([sshUserPrivateKey(credentialsId: 'TEST-Envi', keyFileVariable: 'SSH_KEY')]) {
            // Inside this block, SSH_KEY variable is available
            //sh '''
            //   echo "SSH Key: ${SSH_KEY}"
            //   '''
          script {
           echo "SSH Key: ${SSH_KEY}"
          }
            // Use the private key for some operation (e.g., connecting to a remote server)
            // sh 'ssh -i $SSH_KEY user@remote-server "echo Hello, world!"'
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
