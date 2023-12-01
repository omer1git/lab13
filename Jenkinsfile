def flag = true

pipeline {
    agent any
    parameters {
        string(name: 'VERSION', defaultValue: '', description: 'Version to deploy on prod')
        choice(name: 'DEPLOY_VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Choose a version to deploy')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Execute tests during the build')
    }
       
    environment {
        NEW_VERSION = "${params.DEPLOY_VERSION ?: '1.3.0'}"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
             
                // Define build commands here
                echo "Building version ${NEW_VERSION}"
            }
        }
        stage('Test') {
            when {
                expression { params.executeTests }
            }
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
