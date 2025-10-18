pipeline {
    agent any

    environment {
        APP_NAME = "nodejs-app"
        PORT = "3000"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Surajsharma2210/CI-CD-nodejs-docker-jenkins.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $APP_NAME .'
            }
        }

        stage('Stop Existing Container') {
            steps {
                sh 'docker stop $APP_NAME || true'
                sh 'docker rm $APP_NAME || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d -p $PORT:3000 --name $APP_NAME $APP_NAME'
            }
        }
    }

    post {
        success {
            emailext(
                to: 'ashking4289@gmail.com',
                subject: "SUCCESS: Jenkins Build #${BUILD_NUMBER}",
                body: "🎉 Build #${BUILD_NUMBER} succeeded and deployed on AWS EC2!"
            )
        }
        failure {
            emailext(
                to: 'ashking4289YOUR_EMAIL@gmail.com'@gmail.com',
                subject: "FAILURE: Jenkins Build #${BUILD_NUMBER}",
                body: "⚠️ Build #${BUILD_NUMBER} failed. Please check the logs."
            )
        }
    }
}
