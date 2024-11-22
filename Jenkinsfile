pipeline {
    agent any  // This can be modified to run on a specific node if needed

    environment {
        // You can define environment variables here if needed
        WORKSPACE_DIR = "${env.WORKSPACE}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Clone the Git repository
                echo 'Checking out the code from GitHub repository'
                git 'https://github.com/nehajain221292/jenkins-build-script.git'  // Replace with your repo URL
            }
        }

        stage('Build') {
            steps {
                // Run the build.bat script on Windows
                echo 'Running Hello_World.bat script'
                bat 'Hello_World.bat'  // Runs the batch file in the workspace
            }
        }

        stage('Test') {
            steps {
                // You can add your test steps here if applicable
                echo 'Running tests...'
                // Example: bat 'test.bat' or any other testing command
            }
        }

        stage('Notify') {
            steps {
                // Add any notification steps, like sending an email or posting to a Slack channel
                echo 'Build completed successfully!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
            // You can add actions to notify users about the success, e.g., sending an email
        }

        failure {
            echo 'Pipeline failed.'
            // You can add actions for failure, e.g., sending a failure notification
        }
    }
}
