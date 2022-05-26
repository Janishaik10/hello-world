node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    withSonarQubeEnv('
credentialsId: 'bb7bfdb2f409f6f5daf20892fb0593265e06cb28', installationName: 'sonar-poc' ') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=sonar-pipeline"
    }
  }
}
