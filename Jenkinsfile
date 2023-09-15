pipeline {
    agent { dockerfile true }
    stages {
        stage('Dockerfile') {
                agent any
                steps {
                    git(
                        url: 'https://github.com/rechandler12/szkolenie-cicd-jenkins-gitlab/blob/main/docker-pipeline/Dockerfile',
                        branch: "main"
                    )
        stage('Test') {
            steps {
            sh 'echo Hello work'
            }
        }
    }
}