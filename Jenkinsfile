pipeline {
    agent any

    tools {
        maven "maven-3"
    }

    stages {
        stage('Clean') {
            steps {
                cleanWs()
            }
        }
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/spring-petclinic/spring-framework-petclinic.git'
            }
        }
        stage('Build') {
            steps {
                args '-v /root/.m2:/root/.m2 -v "$pwd":/usr/src/app -w /usr/src/app'
                sh "mvn clean spring-boot:build-image"
            }
            post {
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    slackSend channel: 'jenkins-przemek-piasta', message: "${env.BUILD_TAG} i ${env.BUILD_URL}"
                }
            }
        }
    }
}
