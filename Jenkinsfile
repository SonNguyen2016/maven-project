pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Build stage"'
                sh 'mvn clean package'
                post {
                    success {
                        echo 'Build is successful. Now archiving...'
                        archiveArtifacts artifacts: '**/target/*.war'
                    }
                }
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Test stage"'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo Deploy stage'
            }
        }
    }
}