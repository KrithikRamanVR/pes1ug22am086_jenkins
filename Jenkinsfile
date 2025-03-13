pipeline {
    agent any

    environment {
        FILE_NAME = 'hello.cpp'
        BUILD_NAME = 'pes1ug22am086-1'
    }

    stages {
        stage('Build') {
            steps {
                scripted {
                    sh 'g++ ${FILE_NAME} -o ${BUILD_NAME}'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh './${BUILD_NAME}'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
