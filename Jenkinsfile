node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    withSonarQubeEnv('My SonarQube Server') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=sonar-pipeline"
    }
  }
}
