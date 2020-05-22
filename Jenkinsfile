pipeline {
    agent {label 'master'}
    triggers{
        upstream (upstreamProjects: 'fake', threshold: hudson.model.Result.SUCCESS)   
    }
    parameters{
        string(name: 'BUILD_BRANCH', defaultValue: 'master', description: 'ENTER THE BRANCH NAME')
    }
    stages {
        stage('source'){
            steps {
                git url: 'https://github.com/Nirupam1705/game-of-life.git', branch: "${params.BUILD_BRANCH}"
            }
        }
        stage ('package') {
            steps {
                sh 'mvn clean package'
                
            }
        }

    }
}