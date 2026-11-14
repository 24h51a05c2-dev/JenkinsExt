
pipeline {
    agent any

    stages {

        stage('Git Checkout') {
            steps {
                echo 'Code downloaded from GitHub'
            }
        }

        stage('Compile') {
            steps {
                bat '"C:\\Maven\\apache-maven-3.10.0\\bin\\mvn.cmd" -f JavaApp\\pom.xml clean compile'
            }
        }

        stage('Test') {
            steps {
                bat '"C:\\Maven\\apache-maven-3.10.0\\bin\\mvn.cmd" -f JavaApp\\pom.xml test'
            }
        }

        stage('Package') {
            steps {
                bat '"C:\\Maven\\apache-maven-3.10.0\\bin\\mvn.cmd" -f JavaApp\\pom.xml package'
            }
        }

        stage('Run Application') {
            steps {
                bat 'java -cp JavaApp\\target\\classes com.example.App'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESSFUL!'
        }

        failure {
            echo 'BUILD FAILED!'
        }
    }
}