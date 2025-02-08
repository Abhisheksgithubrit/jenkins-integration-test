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
            jiraAddComment idOrKey: 'KAN-1', comment: "Build & Deployment Successful"
        }
        failure {
            jiraAddComment idOrKey: 'KAN-1', comment: "Build Failed"
        }
    }
}
