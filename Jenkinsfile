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
            agent {
                dockerfile {
                 filename             'Dockerfile'
                    dir                  'docker-pipeline'
                    args                 '-v /tmp:/tmp'
                    }
            }
            steps {
                // sh 'cd ..'
                sh 'ls'
                sh 'echo Hello work'
            }
        }
    }
}