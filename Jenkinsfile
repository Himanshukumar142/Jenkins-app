pipeline {
    agent {
        docker {
            image 'maven:3.9.6-eclipse-temurin-17'
        }
    }

    stages {

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Run') {
            steps {
                sh 'docker run -d -p 8080:8080 my-app'
            }
        }
    }
}