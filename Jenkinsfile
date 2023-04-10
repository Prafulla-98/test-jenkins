pipeline {
    agent any
    environment {
        DOCKERHUB_PASS = credentials('docker-pass')
    }
    stages {
        stage("Clone git repo") {
            steps {
                git credentialsId: 'git_credentials', url: 'https://github.com/Prafulla-98/SWE-645-Docker.git'
            }
        }
    }
}