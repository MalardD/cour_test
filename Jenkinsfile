pipeline {​​​​​
    agent any
    tools {​​​​​
        maven 'Maven'
        jdk 'JDK'
    }​​​​​
    parameters {​​​​​
        booleanParam(name: "Perform release ?", description: '', defaultValue: false)
    }​​​​​
    stages {​​​​​
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
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}