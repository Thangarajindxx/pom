pipeline {
    agent any 
    
    stages {
        stage("code checkout"){
            steps {
                git branch: 'main', credentialsId: '3b3aa6cf-5093-4ac2-9199-1d4905b2b259', url: 'https://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@github.com/Thangarajindxx/pom.git'
            }
        }
    }
    post {
        always {
            emailext body: 'summery success', subject: 'pipeline check', to: 'thangarajvelcloud1718@gmail.com'
        }
    }
}
