pipeline {
    agent any

    environment {
        // Define environment variables
        MAVEN_HOME = '/path/to/maven'
    }

    stages {
        stage('Checkout') {
            steps {
                // Fetch code from a GitHub public repository
                git url: 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                // Use Maven to compile the project
                sh "${MAVEN_HOME}/bin/mvn clean package"
            }
        }

        stage('Test') {
            steps {
                // Run unit tests with Maven
                sh "${MAVEN_HOME}/bin/mvn test"
            }
        }

        stage('Deploy') {
            steps {
                // Deploy your application
                // This is a placeholder for your deployment script
                // Adapt this part to your specific deployment process
                echo 'Deploying application...'
                // e.g., sh 'scripts/deploy.sh'
            }
        }
    }

    post {
        always {
            // Perform actions that should always occur, regardless of stage success/failure
            // Examples: cleanup, sending notifications
            echo 'Pipeline execution complete!'
        }
        success {
            // Actions to perform if the pipeline succeeds
            echo 'Pipeline succeeded!'
        }
        failure {
            // Actions to perform if the pipeline fails
            echo 'Pipeline failed!'
        }
    }
}
