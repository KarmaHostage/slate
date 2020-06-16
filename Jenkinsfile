pipeline {
    agent any

    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh './ci/build.sh'
            }
        }
        stage('Push Docker') {
            steps {
              sh './ci/push.sh'
            }
        }
        stage('Deploy') {
          steps {
            sh './ci/tag-for-deployment.sh'
            sshagent(credentials: ['jenkins-server-login']) {
              sh 'ssh -t -t jenkins@138.201.152.78 -o StrictHostKeyChecking=no "sh rest-docs.sh"'
            }
          }
        }
    }
}
