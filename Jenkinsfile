pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Stage 1: Build - Compiling and packaging the code using Maven"
                    echo "Tool: Maven"
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo "Stage 2: Unit and Integration Tests - Running unit and integration tests"
                    echo "Tool: JUnit for unit tests and TestNG for integration tests"
                }    
            }
            post {
                always {
                    script {
                        mail (
                            to: 'ravindu.w7@gmail.com',
                            subject: "Jenkins: Unit and Integration Tests Stage Successful",
                            body: "The Unit and Integration Tests stage has been successful. Please find the logs attached. \nConsole Output: \${env.BUILD_URL}console",
                            mimeType: 'text/html'
                        )
                    }
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo "Stage 3: Code Analysis - Analyzing code to ensure it meets industry standards"
                    echo "Tool: SonarQube"
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo "Stage 4: Security Scan - Performing a security scan to identify vulnerabilities"
                    echo "Tool: OWASP Dependency-Check"
                }
            }
            post {
                always {
                    script {
                        mail (
                            to: 'ravindu.w7@gmail.com',
                            subject: "Jenkins: Security Scan Stage Successful",
                            body: "The Security Scan stage has been successful. Please find the logs attached. \nConsole Output: \${env.BUILD_URL}console",
                            mimeType: 'text/html'
                        )
                    }
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo "Stage 5: Deploy to Staging - Deploying the application to a staging server"
                    echo "Tool: AWS CLI"
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo "Stage 6: Integration Tests on Staging - Running integration tests in the staging environment"
                    echo "Tool: Selenium for UI tests and Postman for API tests"
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo "Stage 7: Deploy to Production - Deploying the application to a production server"
                    echo "Tool: AWS CLI"
                }
            }
        }
    }
}
