pipeline{
    agent any

    stages{
        stage('Clone'){
            steps{
                checkout scm
            }
        }

        stage('Build Docker Image'){
            steps{
                script{
                    docker.build('simple-html-app')
                }
            }
        }

        stage('Run Container'){
            steps{
                script{
                    bat 'docker rm -f html-container || true'
                    bat 'docker run -d -p 8081:80 --name html-container simple-html-app'
                }
            }
        }

    }
}