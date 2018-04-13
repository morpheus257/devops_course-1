pipeline
{
    agent any
    stages {
        stage('Checkout SCM'){
            steps{
                sh 'git checkout ${BRANCH_NAME}'
            }
        }
        stage('release') {
            when { branch 'master' }
            environment {
                DOCKER_REPOSITORY = 'filippo123456'
            }
            steps {
                  withCredentials([usernamePassword(credentialsId: 'docker_login', usernameVariable: 'USER', passwordVariable: 'PSW')]) {
                    sh 'docker login -u $(USER) -p $(PSW)'
                  }
                  sshagent (credentials: ['GitHub'] {
                  sh 'sbt "release with-defaults"'
            }
        }
    }
    post {
        always {
            deleteDir()
    }
    }
}