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
        stage("Building the Student Survey Image") {
            steps {
                script {
                    checkout scm
                    DATE_TAG = java.time.LocalDate.now()
                    DATETIME_TAG = java.time.LocalDateTime.now()
                    sh "echo ${DATETIME_TAG}"
                    sh "docker login -u prafulladevi -p ${DOCKERHUB_PASS}"
                    def customImage = docker.build("prafulladevi/swe645-project2:${DATETIME_TAG}")
                }
            }
        }
    }
}
