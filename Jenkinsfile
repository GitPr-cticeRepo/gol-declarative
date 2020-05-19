pipeline {
    agent {label 'MASTER'}
	triggers {
	   upstream(upstreamProjects: 'dummy-fs', threshold: hudson.model.Result.SUCCESS)
	}
    stages {
        stage('Source'){
            steps {
                git 'https://github.com/GitPr-cticeRepo/gol-declarative.git' 
            }
        }
        stage('Package'){
            steps {
                sh 'mvn package'
				input 'continue to next step?'
				archiveArtifacts 'gameoflife-web/target/*.war'
            }
        }
    }
}
