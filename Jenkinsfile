pipeline {​​​​​
    agent any
    tools {​​​​​
        maven 'maven'
        jdk 'jdk11'
    }​​​​​
    parameters {​​​​​
        booleanParam(name: "Perform release ?", description: '', defaultValue: false)
    }​​​​​
    stages {​​
        stage('Example')​​​{
         steps {
                        sh 'mvn --version'
                    }
        }
        stage('Initialize') {​​​​​
            steps {​​​​​
                sh '''
                    echo "PATH = ${PATH}​​​​​"
                    echo "M2_HOME = ${M2_HOME}​​​​​"
                '''
            }​​​​​
        }​​​​​
        stage('Build') {​​​​​
            steps {​​​​​
                sh 'mvn compile'
            }​​​​​
        }​​​​​
        stage('Test') {​​​​​
            steps {​​​​​
                sh 'mvn test'
            }​​​​​
        }​​​​​

        }​​​​

        }
        ​​​​
