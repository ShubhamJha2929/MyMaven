pipeline {
    agent any

    tools {
        maven 'Maven '       // Make sure this is the exact name defined in Jenkins > Global Tool Configuration
                      // Same here
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                git branch: 'master', url: 'https://github.com/ShubhamJha2929/MyMaven.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building project with Maven...'
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Running application...'
                sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed!'
        }
    }
}

