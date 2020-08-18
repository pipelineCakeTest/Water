pipeline {
    agent any

    stages {
        stage('Prepare Environment') {
            steps {
                script {
                    checkout scm
                    githubNotify account: 'pipelineCake', context: 'Final Test', credentialsId: 'Github',
                        description: 'This is an example', repo: 'Water', sha: GIT_COMMIT,
                        status: 'PENDING', targetUrl: RUN_DISPLAY_URL
                }
            }
        }
    }
    post {
        always {
            script {
                githubNotify account: 'pipelineCake', context: 'Final Test', credentialsId: 'Github',
                    description: 'This is an example', repo: 'Water', sha: GIT_COMMIT,
                    status: 'SUCCESS', targetUrl: RUN_DISPLAY_URL
            }
        }
    }
}
