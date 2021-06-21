pipeline {
    agent any
    stages {
        stage('git repo & clean') {
            steps {
                 sh "rm -rf jenkins_learning"
                sh "git clone https://github.com/prasanna-tunga23/jenkins_learning.git"
                sh "mvn clean -f jenkins_learning"
            }
        }
        stage('install') {
            steps {
                sh "mvn install -f jenkins_learning"
            }
        }
        stage('test') {
            steps {
                sh "mvn test -f jenkins_learning"
            }
        }
        stage('package') {
            steps {
                sh "mvn package -f jenkins_learning"
            }
        }
    }
}
