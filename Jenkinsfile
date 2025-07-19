pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
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
