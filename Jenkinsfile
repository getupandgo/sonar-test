
node {
  stage('SCM') {
    git 'https://github.com/getupandgo/sonar-test.git'
  }
  stage('SonarQube analysis') {
      environment {
          scannerHome = tool 'SonarQubeScanner'
      }
    withSonarQubeEnv('sonar-instance') {
      sh "${scannerHome}/bin/sonar-scanner -X"
    }
  }
}