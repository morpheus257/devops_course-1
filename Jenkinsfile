pipeline {
    agent any
    stages {
        stage('Checkout SCM'){
            steps{
                checkout scm
            }
        }
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