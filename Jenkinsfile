pipeline {
    agent any

    stages {

        stage('Checkout from GitHub') {
            steps {
                git branch: 'main', url: 'https://github.com/USERNAME/REPO_NAME.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t static-site .'
            }
        }

        stage('Run Container') {
            steps {
                bat 'docker run -d -p 80:80 --name static-site static-site'
            }
        }
    }
}
