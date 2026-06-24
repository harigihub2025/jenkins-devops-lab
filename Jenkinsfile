pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t myapp:v2 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'sudo docker rm -f myapp-container || true'
                sh 'sudo docker run -d -p 8081:80 --name myapp-container myapp:v2'
            }
        }

    }
}
