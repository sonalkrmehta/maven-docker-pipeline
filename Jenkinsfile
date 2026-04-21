pipeline {
    agent any

    environment {
        IMAGE_NAME = "demo-jenkins-app"
    }

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/sonalkrmehta/https://github.com/sonalkrmehta/maven-docker-pipeline.git'
            }
        }

        stage('Build Maven') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8080:8080 $IMAGE_NAME'
            }
        }
    }
}
