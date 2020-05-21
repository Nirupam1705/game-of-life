pipeline {
    agent {label 'master'}
    stages {
        stage('source'){
            steps {
                git 'https://github.com/Nirupam1705/game-of-life.git'
            }
        }
        stage ('package') {
            steps {
                sh 'mvn clean package'
            }
        }

    }
}