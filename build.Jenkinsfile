pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
        stage('Trigger Deploy') {
             steps {
                build job: 'RobertaDeploy', wait: false, parameters: [
                string(name: 'ROBERTA_IMAGE_URL', value: "<full-url-to-docker-image>")
                ]
            }
        }
    }
}
