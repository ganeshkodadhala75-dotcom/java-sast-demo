pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source code is checked out from GitHub'
            }
        }

        stage('SonarQube Scan') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    sh '''
                    sonar-scanner \
                    -Dsonar.projectKey=java-sast-demo \
                    -Dsonar.projectName=java-sast-demo \
                    -Dsonar.sources=src
                    '''
                }
            }
        }
    }
}
