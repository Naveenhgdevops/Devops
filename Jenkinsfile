pipeline {
    agent any
    tools {
        maven 'localMaven'
    }
    stages{
            stage('Build Java Application'){
                steps {
                    sh 'mvn clean package'
                }
                post {
                    success {
                        echo 'Archiving the artifacts'
                        archiveArtifacts artifacts: '**/target/*.war'
                    }
                }
            }
            stage('Deployment to Staging server'){
                parallel{
                    stage('Deploy to Tomcat Server'){
                        steps{
                            deploy adapters: [tomcat9(credentialsId: 'tomcat-b12', path: '', url: 'http://15.206.167.147:8080/')], contextPath: null, war: '**/*.war'
                        }
                    }

                }

            }
        }
}
