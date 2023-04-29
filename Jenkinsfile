pipeline{
    agent any
    stages{
        stage('Delete existing docker image'){
            steps{
            checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/aditya8905/html']])
            script{
            bat 'docker rmi -f adityamaharshi/html:latest'
            }
            }
        }
        stage('Build Docker image'){
            steps{
            script{
            bat 'docker build -t adityamaharshi/html .'
            }
            }
        }
        stage('Push image to Docker Hub'){
            steps{
            script{
            bat 'docker login -u "adityamaharshi" -p "969451412412@Sh" docker.io'
            bat 'docker push adityamaharshi/html:latest'
            }
            }
        }
    }
}