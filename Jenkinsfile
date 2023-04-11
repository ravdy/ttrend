pipeline {
    agent {
        node {
            label 'maven-agent'
        }
    }

    stages {
        stage('Clone code') {
            steps {
                git branch: 'main', url: 'https://github.com/ravdy/ttrend.git'
            }
        }
    }
}
