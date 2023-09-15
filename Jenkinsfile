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
            // agent {
            //     dockerfile {
            //      filename             'Dockerfile.build'
            //         dir                  'szkolenie-cicd-jenkins-gitlab/docker-pipeline'
            //         args                 '-v /tmp:/tmp'
            //         }
            // }
            steps {
                dir("${env.WORKSPACE}/build-pipeline"){
                    sh "pwd"
                    sh 'ls -al'
                }


            }
        }
    }
}