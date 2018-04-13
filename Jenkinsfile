pipeline {
    agent any
    stages {
        stage('release') {
            when { branch 'master' }
            environment {
                DOCKER_REPOSITORY = 'filippo123456'
            }
            steps {
                sh 'sbt release'
            }
        }
    }
}