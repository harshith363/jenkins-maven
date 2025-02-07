pipeline {
    agent any
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
