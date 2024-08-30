pipeline {
    agent any

    tools {
        maven 'Maven 3.8.6'
        jdk 'JDK 11'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the code using Maven...'
                sh 'mvn clean install'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                sh 'mvn test'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis with SonarQube...'
                sh 'mvn sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dsonar.login=YOUR_SONARQUBE_TOKEN'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan with OWASP Dependency-Check...'
                sh 'dependency-check.sh --project MyProject --out . --scan ./src'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying application to staging server...'
                // Add deployment commands here
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging environment...'
                // Add integration test commands here
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying application to production server...'
                // Add production deployment commands here
            }
        }
    }

    post {
        success {
            mail to: 'yuvindeakin@gmail.com',
                 subject: "Build Successful: ${JOB_NAME} #${BUILD_NUMBER}",
                 body: """\
The build was successful.

Job: ${JOB_NAME}
Build Number: ${BUILD_NUMBER}
Build URL: ${BUILD_URL}
"""
        }
        failure {
            mail to: 'yuvindeakin@gmail.com',
                 subject: "Build Failed: ${JOB_NAME} #${BUILD_NUMBER}",
                 body: """\
The build failed.

Job: ${JOB_NAME}
Build Number: ${BUILD_NUMBER}
Build URL: ${BUILD_URL}
""",
                 attachLog: true
        }
    }
}
