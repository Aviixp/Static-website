pipeline {
    agent any

    stages {

        stage('Checkout from GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/Aviixp/Static-website.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t static-site:101 .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 3690:80 --name s9 static-site'
            }
        }
    }
}
