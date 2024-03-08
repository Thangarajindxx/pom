pipeline {
    agent any 

    stages {
        stage ('Build') {
            steps{
                sh 'mvn clean package'
            }
            post {
                success{
                    echo "Archiving the artifacts"
                    ArchiveArtifacts artifacts: '**/target/*.war'
                }
            }

        }
        stage ('Deploy to Tomcat server') {
            steps{
                deploy adapters: [tomcat9(credentialsId: '3b3aa6cf-5093-4ac2-9199-1d4905b2b259', path: '', url: 'http://3.19.72.119:8090/')], contextPath: null, war: '**/target/*.war'
            }
        }
    }
}
