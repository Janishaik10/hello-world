pipeline {
    agent any
    stages {
        stage('scm checkout') {
            steps {
                sh 'https://github.com/Janishaik10/hello-world.git'
            }
        }
        stage('SonarQube analysis 1') {
            steps {
                sh 'clean install sonar:sonar'
            }
        }
        stage("Quality Gate 1") {
            steps {
                waitForQualityGate abortPipeline: true
            }
        }
        stage('SonarQube analysis 2') {
            steps {
                sh 'maven sonarqube'
            }
        }
        stage("Quality Gate 2") {
            steps {
                waitForQualityGate abortPipeline: true
            }
        }
    }
}
