node {
  stage('Clone the Git') {
    git 'https://github.com/Ayushi26Bhagat/sonarqube-jenkinspipeline.git'
  }
  stage('SonarQube analysis') {
    def scannerHome = tool 'sonar';
    withSonarQubeEnv('sonar') {
      sh "${scannerHome}/bin/sonar-scanner \
      -D sonar.login=admin \
      -D sonar.password=admin \
      -D sonar.projectKey=sonarqubetest \
      -D sonar.exclusions=vendor/**,resources/**,**/*.java \
      -D sonar.host.url=http://localhost:9000/"
    }
  }
}
