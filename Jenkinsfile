pipeline {
    agent {
        docker {
            image 'maven:3.8.5' // Uses Maven Docker Image
        }
    }
    stages {
        stage('Checkout') {
            steps {
                git branch:'main', url:'https://github.com/harshith363/jenkins-maven.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Archive Artifacts') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}
