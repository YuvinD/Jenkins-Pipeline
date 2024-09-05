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
                    echo 'Running unit tests using JUnit...'
                    echo 'Running integration tests using TestNG...'
                }
            }
            post {
                success {
                    emailext(
                        subject: 'Unit and Integration Tests Success',
                        body: 'Unit and integration tests passed successfully.',
                        to: 'yuvindeakin@gmail.com',
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        subject: 'Unit and Integration Tests Failure',
                        body: 'Unit or integration tests failed.',
                        to: 'yuvindeakin@gmail.com',
                        attachLog: true
                    )
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
            post {
                success {
                    emailext(
                        subject: 'Security Scan Success',
                        body: 'Security scan completed successfully.',
                        to: 'yuvindeakin@gmail.com',
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        subject: 'Security Scan Failure',
                        body: 'Security scan failed.',
                        to: 'yuvindeakin@gmail.com',
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying application to AWS EC2 staging server...'
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
                    echo 'Deploying application to AWS EC2 production server...'
                }
            }
        }
    }
    post {
        success {
            emailext(
                subject: 'Pipeline Success',
                body: 'Pipeline ran successfully.',
                to: 'yuvindeakin@gmail.com',
                attachLog: true
            )
        }
        failure {
            emailext(
                subject: 'Pipeline Failure',
                body: 'Pipeline failed.',
                to: 'yuvindeakin@gmail.com',
                attachLog: true
            )
        }
    }
}
