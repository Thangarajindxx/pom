pipeline {
    agent any 
    
    tools {node 'nodejs'}
    
    stages {
        stage ('git clone'){
            steps {
                git branch: 'main', url: 'https://github.com/Thangarajindxx/pom.git'
            }
        }
        stage ('maven build'){
            steps {
                sh 'mvn clean install'
            }
        }
        stage ('test'){
            steps {
                echo "code test completed"
            }
        }
        stage ('code deploy'){
            steps {
                echo"code deploy in progress"
            }
        }
    }
}
