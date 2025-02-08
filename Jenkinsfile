pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
    post {
        success {
            jiraAddComment(site: 'abhialavandi.atlassian.net', idOrKey: 'KAN-1', comment: 'Build successful!')
        }
        failure {
            jiraAddComment(site: 'abhialavandi.atlassian.net', idOrKey: 'KAN-1', comment: "Build Failed")
        }
    }
}
