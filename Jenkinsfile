pipeline {
    agent any

    triggers {
        pollSCM('H/5 * * * *') // Polls GitHub every 5 minutes
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/PadminiPriyanka28/ColorApp.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'echo "Building the application..."'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'echo "Running tests..."'
                }
            }
        }

        stage('Deploy (Optional)') {
            steps {
                script {
                    sh 'echo "Deploying application..."'
                }
            }
        }
    }

    post {
        success {
            mail to: 'poreddyppriyanka@gmail.com',
                 subject: "Jenkins Build Success",
                 body: "The build was successful."
        }
        failure {
            mail to: 'poreddyppriyanka@gmail.com',
                 subject: "Jenkins Build Failed",
                 body: "The build has failed. Please check Jenkins logs."
        }
    }
}
