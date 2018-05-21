pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Build stage'
                sh 'mvn clean package'
            }
            post {
                success {
                echo 'Build is successful. Now archiving...'
                archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage('Deploy to staging') {
            steps {
                build job: 'deploy-to-staging'
            }
        }
    }
}