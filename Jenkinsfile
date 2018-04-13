pipeline {
    agent any
    stages {
        stage('Checkout SCM'){
            steps{
                sh 'git checkout ${env.BRANCH_NAME}'
            }
        }
        stage('release') {
            when { branch 'master' }
            environment {
                DOCKER_REPOSITORY = 'filippo123456'
            }
            steps {
                sh 'sbt "release with-defaults"'
            }
        }
    }
}