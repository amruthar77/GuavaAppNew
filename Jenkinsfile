pipeline {
    agent any

    tools {
        maven 'Maven'
        jdk 'JDK'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/amruthar77/GauvaAppNew.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Run') {
            steps {
                sh 'java -jar target/GauvaAppNew-1.0-SNAPSHOT.jar'
            }
        }
    }
    post {

        success {
            echo 'Build and execution successful '
        }

        failure {
            echo 'Build failed '
        }
        }
}
