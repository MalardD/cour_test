pipeline {
    agent any
    tools {
        maven 'maven'
        jdk 'jdk11'
    }
    parameters {
        booleanParam(name: "Performrelease ?", description : '', defaultValue: false)
    }
    stages {
        stage('Initialize') {
            steps {
                bat '''
                    echo "PATH ${PATH}"
                    echo "M2_HOME ${M2_HOME}"
                '''
            }
        }
        stage('Build') {
            steps {
                bat 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Sonarqube') {
                    environment {
                        scannerHome = tool 'sonarScanner4'
                    }
                    steps {
                        withSonarQubeEnv('sonarqube') {
                            sh "${scannerHome}/bin/sonar-scanner"
                        }
                        timeout(time: 10, unit: 'MINUTES') {
                            waitForQualityGate abortPipeline: true
                        }
                    }
                }
    }
}
