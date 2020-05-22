pipeline {
    agent {label 'master'}
    triggers{
        upstream (upstreamProjects: 'fake', threshold: hudson.model.Result.SUCCESS)
        corn('* * * * *')
    }
    stages {
        stage('source'){
            steps {
                git 'https://github.com/Nirupam1705/game-of-life.git'
            }
        }
        stage ('package') {
            steps {
                sh 'mvn clean package'
                input  'execute this step'
            }
        }

    }
}