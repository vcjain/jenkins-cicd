pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building branch ${env.BRANCH_NAME}"
                // Add build steps here
            }
        }
        stage('Test') {
            steps {
                echo "Testing branch ${env.BRANCH_NAME}"
                // Add test steps here
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying branch ${env.BRANCH_NAME}"
                // Add deploy steps here
            }
        }
    }
}
