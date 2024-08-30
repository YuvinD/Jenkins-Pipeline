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
