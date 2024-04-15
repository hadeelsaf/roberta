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
                  sh 'python3 -m pylint -f parseable --reports=no *.py > pylint.log'
                }
            post {
                  always {
                   sh 'cat pylint.log'
                   recordIssues (
                      enabledForFailure: true,
                      aggregatingResults: true,
                      tools: [pyLint(name: 'Pylint', pattern: '**/pylint.log')]
                   )
                   }
            }
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