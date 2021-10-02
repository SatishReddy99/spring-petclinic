pipeline {
  agent any
    stages {
        stage("checkout the code ") {
            steps {
                sh "checkout scm"
            }
        }

    post {
        always {
            sh " ls || true"
        }

        success {
            bitbucketStatusNotify buildState: "SUCCESSFUL"
        }

        failure {
            bitbucketStatusNotify buildState: "FAILED"
        }
    }
}
