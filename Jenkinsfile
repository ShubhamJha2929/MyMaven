'pipeline {
    agent any

    tools {
        // Install and use Maven and JDK by name (must be pre-configured in Jenkins)
        maven 'Maven 3.8.6'       // Replace with your Maven installation name in Jenkins
        jdk 'JDK 11'              // Replace with your JDK installation name in Jenkins
    }

    
    

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                git branch:'master', url: 'https://github.com/ShubhamJha2929/MyMaven.git'
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
               sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
            }
        }

    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

