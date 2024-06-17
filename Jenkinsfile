pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Add build steps here, e.g., compile code
            }
        }
        
        stage('QA') {
            steps {
                echo 'QA Testing using SOnarQube...'
                // Add testing steps here, e.g., run unit tests
            }
        }
        
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add deployment steps here, e.g., deploy to a server
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
