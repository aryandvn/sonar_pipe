pipeline {
  agent {label 'linux'}
  options {
      buildDiscarder(logRotator(numToKeepStr: '$'))
  }
  stages {
    steps {
      withSonarQubeEnv(installationName: 'SONAR-1') {
        sh './mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin::sonar'
      }
    }
   }
}
