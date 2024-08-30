pipeline {
    agent any
    tools {
        maven 'Maven 3.9.9'
        jdk 'JDK 17'
    }
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Using Maven for build stage'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Using Maven for unit and integration tests'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Using SonarQube for code analysis'
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Using OWASP Dependency-Check for security scan'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying to staging server'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to production server'
                }
            }
        }
    }
    post {
        always {
            mail(
                to: 'yuvindeakin@gmail.com',
                subject: "Build ${currentBuild.fullDisplayName}",
                body: "Build ${currentBuild.fullDisplayName} completed with status: ${currentBuild.currentResult}. See ${env.BUILD_URL} for details."
            )
        }
    }
}
