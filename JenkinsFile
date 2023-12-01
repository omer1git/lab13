pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Define build commands here
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Define test commands here
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Define deployment commands here
            }
        }
    }
    post {
        always {
            echo 'Post-build actions always run'
        }
        failure {
            echo 'Post-build actions if the build fails'
        }
    }
}
