pipeline {
    agent any
    stages {
        stage('Dockerfile') {
                agent any
                steps {
                    git(
                        url: 'https://github.com/rechandler12/szkolenie-cicd-jenkins-gitlab/',
                        branch: "main"
                    )
                }
        }
        stage('Test') {
            //agent {
            //    dockerfile true
            //}
            steps {
            sh cd ..
            sh pwd
            sh 'echo Hello work'
            }
        }
    }
}