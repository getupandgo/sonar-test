
node {
  stage('SCM') {
    git 'https://github.com/getupandgo/sonar-test.git'
  }
  stage('SonarQube analysis') {
    // requires SonarQube Scanner 2.8+
    def scannerHome = tool 'sonar-scanner';
    withSonarQubeEnv('sonar-instance') {
      sh "${scannerHome}/bin/sonar-scanner -X"
    }
  }
}