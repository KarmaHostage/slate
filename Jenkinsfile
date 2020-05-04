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
    }
}
