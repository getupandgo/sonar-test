
node {
  stage('SCM') {
    git 'https://github.com/getupandgo/sonar-test.git'
  }
  stage('SonarQube analysis') {
    // requires SonarQube Scanner 2.8+
    def scannerHome = tool 'sonar-scanner';
    withSonarQubeEnv('sonar-server') {
      sh "${scannerHome}/bin/sonar-scanner -X"
    }
  }
}