pipeline {
    agent any
    
    tools {
        maven 'Maven 3.9.7'
    }

    environment {
        GIT_REPO = 'https://github.com/thabassum1219/Declarative_Pipeline_Forked.git'
        BRANCH = 'master'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the code...'
                git branch: "${BRANCH}", url: "${GIT_REPO}"
            }
        }

        stage('Build') {
            steps {
                echo 'Building the code...'
                // Use the Maven tool configured in Jenkins
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add your deployment steps here
            }
        }
    }

    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
    }
}

