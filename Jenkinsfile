pipeline {
    agent any
    stages {
        stage('Docker version') {
            steps {
                sh 'docker version'
            }
        }

        // Source: https://jenkins.io/doc/book/pipeline/docker/
        stage('Back-end') {
            agent {
                docker { image 'maven:3-alpine' }
            }
            steps {
                sh 'mvn --version'
            }
        }
        stage('Front-end') {
            agent {
                docker { image 'node:7-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
    }
}
