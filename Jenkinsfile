pipeline {
    agent {
        docker { image 'node:20.10.0-alpine3.19' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
        stage('Fail') {
            steps {
                sh 'echo "Fail"'
                sh 'exit 1'
            }
        }
        stage('Done') {
            always {
                echo 'always'
            }
            failure {
                echo 'failed'
            }
            changed {
                echo 'changed'
            }
        }
    }
}
