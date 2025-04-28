pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("python-cicd-demo:${env.BUILD_ID}")
                }
            }
        }

        stage('Run App') {
            steps {
                sh 'docker run --rm python-cicd-demo:${BUILD_ID}'
            }
        }
    }
}
