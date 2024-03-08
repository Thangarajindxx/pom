pipeline {
    agent any 
    tools {
        maven 'Maven'
        jdk 'JDK'// Adjust this if the Maven installation name is different
    }
    stages {
        stage ('Build') {
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo "Archiving the artifacts"
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage ('Deploy to Tomcat server') {
            steps {
                deploy war: '**/target/*.war', tomcat: [credentialsId: '3b3aa6cf-5093-4ac2-9199-1d4905b2b259', url: 'http://3.19.72.119:8090/']
            }
        }
    }
}
