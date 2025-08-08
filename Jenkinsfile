pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                echo 'clone code............'
                checkout scm
            }
        }
        stage('build imgae') {
            steps {
                echo 'Hello World deploy 222222'
                sh 'docker build -t 111 .'
                sh 'docker run -p 8085:80 111'

            }
        }
    }
}
