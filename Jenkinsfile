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
                bat 'docker compose up -- build --abort-on-container-exit'
            }
        }

        stage('push to release') {
            steps {
                bat 'git branch release'
                bat 'git switch release'
                bat 'git push --verbose origin release'
            }
        }

        stage('success') {
            steps {
                bat 'echo SUCCESS'
            }
        }
    }
}