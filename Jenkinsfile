pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Notify Slack') {
            steps {
                slackSend (
                    channel: '#jenkins-alerts', // Replace with your Slack channel
                    message: "Jenkins Build Successful!", // Customize your message
                    color: "good" // "good", "warning", or "danger"
                )
            }
        }
    }
    post {
        failure {
            slackSend (
                channel: '#jenkins-alerts', // Replace with your Slack channel
                message: "Jenkins Build Failed!", // Customize your message
                color: "danger" // "good", "warning", or "danger"
            )
        }
    }
}
