pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/yulakhraj/JenkinsDocker-Demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-tomcat-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8084:8080 --name tomcat-jenkins my-tomcat-app'
            }
        }
    }
}
