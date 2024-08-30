pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the code using Maven...'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running unit tests with JUnit and integration tests with TestNG...'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Analyzing code with SonarQube...'
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Performing security scan with OWASP ZAP...'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying application to AWS EC2 instance...'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging environment...'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying application to production server on AWS EC2 instance...'
                }
            }
        }
    }

    post {
        always {
            script {
                echo 'Sending notification email to yuvindeakin@gmail.com...'
            }
        }
        success {
            script {
                echo 'Build succeeded!'
            }
        }
        failure {
            script {
                echo 'Build failed!'
            }
        }
    }
}
