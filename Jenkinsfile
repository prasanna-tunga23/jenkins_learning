pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v /root/.m2:/root/.m2'
        }
    }
    stages {
        stage('git repo & clean') {
            steps {
                 sh "rm -rf jenkins_learning"
                sh "git clone https://github.com/prasanna-tunga23/jenkins_learning.git"
//                 sh "mvn clean -f jenkins_learning"
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -B -DskipTests clean package'
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
