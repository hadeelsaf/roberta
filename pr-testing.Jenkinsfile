pipeline {
    agent any

    stages {
        stage('Unittest') {
            post {
                always {
                    junit allowEmptyResults: true, testResults: 'results.xml'
                }
            steps {
                echo "testing"
            }
        }
        stage('Lint') {
            steps {
                echo "linting"
            }
        }
        stage('Functional test') {
            steps {
                echo "testing"
            }
        }
    }
}