pipeline {
    agent any

    stages {
        stage('Prepare Environment') {
            steps {
                script {
                    githubNotify description: 'The build just start',  status: 'PENDING'
                }
            }
        }
    }
    post {
        always {
            script {
                githubNotify description: 'The build is over',  status: 'SUCCESS'
            }
        }
    }
}