pipeline {
    agent { label 'LINUX' }
    triggers { pollSCM('* * * * *') }
    stages {
        stage('clone and compile') {
            steps {
                git branch: 'declarative', 
                url: 'https://github.com/GitPr-cticeRepo/gol-declarative.git'
                sh 'mvn compile'
            }
        }
    }
}