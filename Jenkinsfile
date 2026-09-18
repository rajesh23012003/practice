pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                checkout scm
            }
        }

        stage('Show Files') {
            steps {
                bat '''
                    echo ================================
                    echo Files in workspace
                    echo ================================
                    dir
                '''
            }
        }

        stage('Read File') {
            steps {
                bat '''
                    echo ================================
                    echo Contents of index.txt
                    echo ================================
                    type index.txt
                '''
            }
        }

        stage('Build') {
            steps {
                bat '''
                    echo ================================
                    echo Build Started
                    echo ================================
                    echo Build Number: %BUILD_NUMBER%
                    echo Build completed successfully!
                '''
            }
        }
    }

    post {
        success {
            echo 'Jenkins Pipeline completed successfully!'
        }

        failure {
            echo 'Jenkins Pipeline failed!'
        }
    }
}
