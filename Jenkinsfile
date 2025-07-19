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
                // Use 'bat' for Windows agents
                bat 'docker build -t my-tomcat-app .'
            }
        }

        stage('Run Container') {
            steps {
                // Use 'bat' for Windows agents
                bat 'docker run -d -p 8084:8080 --name tomcat-jenkins my-tomcat-app'
            }
        }
    }
    post {
        always {
            echo 'Cleaning up the container...'
            // Stop and remove the container. The '|| true' prevents the
            // pipeline from failing if the container doesn't exist.
            bat 'docker stop tomcat-jenkins || true'
            bat 'docker rm tomcat-jenkins || true'
        }
    }
}
