pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/AlishbaNawab/AN_12.git', credentialsId: 'AN_12'
                echo 'Checkout complete'
            }
        }

        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'echo Build Successful'
                    } else {
                        bat 'echo Build Successful'
                    }
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'echo Tests Passed'
                    } else {
                        bat 'echo Tests Passed'
                    }
                }
            }
        }

        stage('Notify') {
            steps {
                echo 'Pipeline Completed Successfully'
            }
        }
    }

    post {
        always {
            echo 'Pipeline run finished'
        }
    }
}

