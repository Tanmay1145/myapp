pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git url: 'https://github.com/Tanmay1145/myapp.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Run') {
            steps {
                sh 'docker rm -f myapp_container || true'
                sh 'docker run -d -p 8095:80 --name myapp_container myapp:latest'
            }
        }
    }
}
