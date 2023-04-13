pipeline {
    agent {
        node {
            label 'maven-agent'
        }
    }

environment {
    PATH = "/opt/apache-maven-3.9.1/bin:$PATH"
}
    stages {
        stage('build'){
            steps {
                sh 'mvn clean deploy'
            }
        }
        stage('SonarQube analysis') {
            environment {
            scannerHome = tool 'Valaxy-SonarScanner'
            }
        steps { 
        withSonarQubeEnv('Valaxy-SonarQube-Server') { // If you have configured more than one global server connection, you can specify its name
            sh "${scannerHome}/bin/sonar-scanner"
    }
  }
    }
}
}
