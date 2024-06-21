pipeline {
    agent any

    tools {
        maven 'local-maven' // Adjust with your Maven tool name if needed
    }

    stages {
        stage('Build') {
            steps {
                // Your build steps here
            }
        }
        stage('Deploy to Tomcat Server') {
            steps {
                deploy adapters: [tomcat7(credentialsId: '4f2c3e54-2692-404f-bdce-98d700b0189e', url: 'http://172.20.10.2:8181')], contextPath: '/', war: '**/*.war'
            }
        }
    }

    // Post-build actions, notifications, etc.
}
