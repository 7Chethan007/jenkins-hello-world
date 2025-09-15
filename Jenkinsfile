pipeline {
    agent any

    tools {
        maven "M398"
        jdk "jdk17"
    }

    stages {
        stage('Echo Version') {
            steps {
                sh 'echo Print Maven Version'
                sh 'mvn -version'
                sh 'javac -version'
            }
        }

        stage('Build') {
            steps {
                // git branch: 'main', url: 'https://github.com/7Chethan007/jenkins-hello-world.git'
                sh "mvn clean package -DskipTests=true"
            }
        }

        stage('Unit Test') {
            steps {
                script {
                    for (int i = 0;i < 60; i++) {
                        echo "${i + 1}"
                        sleep 1
                    }
                    sh "mvn test"
                }
            }
        }
    }
}
