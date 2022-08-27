pipeline {
    agent any 
        stages{
            stage('Run quality checks'){
                when {
                    branch 'main' 
                }
              steps {
                    sh '/var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/sonar/bin/sonar-scanner \
  -Dsonar.projectKey=son2 \
  -Dsonar.sources=. \
  -Dsonar.host.url=http://54.197.145.2:9000 \
  -Dsonar.login=sqp_8be7a1aeb82454ca84ee2b930e7f290c3d39165c'
            }
        }
        
    }
}
