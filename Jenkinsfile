pipeline {
    agent any

    stages {
        stage('git checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/jacksontechtraining/sapmlespring001']]])
            }
        }
        stage('compile') {
            steps {
                echo 'compiling project'
                bat 'mvn compile'
            }
        }
        stage('package') {
            steps {
                echo 'packaging application'
                bat 'mvn package'
            }
        }
        stage('install') {
            steps {
                echo 'installing dependency'
                bat 'mvn install'
            }
        }
        stage('test') {
            steps {
                echo 'testing applicaton'
                bat 'mvn test'
            }
        }
    }
}
