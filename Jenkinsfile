pipeline {
    agent any

    tools {
        maven 'Maven3'      // Name configured in Jenkins Global Tool Config
        jdk 'JDK8'        // Name configured in Jenkins
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master',
                url: 'https://github.com/sweta-suman1/TYITA.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}
