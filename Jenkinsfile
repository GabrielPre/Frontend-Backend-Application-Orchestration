pipeline {
    agent any

    stages {
        stage('docker compose build') {
            steps {
                bat 'docker compose build'
            }
        }        
        
        stage('docker compose up') {
            steps {
                bat 'docker compose up --abort-on-container-exit'
            }
        }

        stage('merge from develop and push to release') {
            steps {
                git([url:'https://github.com/GabrielPre/Frontend-Backend-Application-Orchestration/',branch:'release'])
                bat "git checkout release"
                bat "git merge origin/develop"
                bat "git push --set-upstream origin release"
            }
        }

        stage('success') {
            steps {
                bat 'echo SUCCESS'
            }
        }
    }
}