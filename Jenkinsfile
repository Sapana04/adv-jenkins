pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/Sapana04/adv-jenkins.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t demo-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f demo-container || true'
                sh 'docker run -d -p 3000:3000 --name demo-container demo-app'
            }
        }
    }
}
