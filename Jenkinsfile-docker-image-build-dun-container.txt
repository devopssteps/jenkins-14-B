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
                //sh 'docker run -p 8085:80 111'
                sh "docker run -d -p 8085:80 --name demo-container 111:latest"


            }
        }
    }
    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
