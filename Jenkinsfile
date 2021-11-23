pipeline{
    agent any
    stages{
        stage('Sonar Analysis'){
             environment {
              SCANNER_HOME = tool 'SonarQubeScanner'
            }
            steps {
                withSonarQubeEnv(installationName: 'SonarCloudOne', credentialsId: 'elatedstone') {
                    sh '''$SCANNER_HOME/bin/sonar-scanner -Dsonar.organization=elatedstone \
                    -Dsonar.projectKey=elatedstone_notejam-mysql \
                    -Dsonar.sources=. \
	                -Dsonar.branch.name=${BRANCH_NAME} \
                    -Dsonar.host.url=https://sonarcloud.io'''
                }
            }
        }       
    }
}
