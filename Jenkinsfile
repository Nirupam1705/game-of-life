pipeline {
    agent {label 'master'}
    triggers{
        upstream (upstreamProjects: 'fake', threshold: hudson.model.Result.SUCCESS)   
    }
    parameters{
        string(name: 'BUILD_BRANCH', defaultValue: 'MASTER', description: 'ENTER THE BRANCH NAME')
    }
    stages {
        stage('source'){
            steps {
                git 'https://github.com/Nirupam1705/game-of-life.git'
                ${params.BUILD_BRANCH}
            }
        }
        stage ('package') {
            steps {
                sh 'mvn clean package'
                
            }
        }

    }
}