pipeline {
    agent any
    
    tools {
        maven 'local_maven'
    }
stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
        }

        stage ('Deployments'){
                stage ("Deploy to Staging"){
                    steps {
                        sh "scp -v -o StrictHostKeyChecking=no **/*.war root@${params.staging_server}:/opt/tomcat/webapps/"
                    }
                }
            }
        }
}
