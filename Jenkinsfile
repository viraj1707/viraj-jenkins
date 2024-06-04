pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Retrieving source code from the directory path set in the environment variable."
                echo "Building the code and producing required artifacts."
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Executing unit tests."
                echo "Executing integration tests."
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Analyzing code quality using a code analysis tool."
            }
        }

        stage('Security Assessment') {
            steps {
                echo "Scanning for vulnerabilities with a security tool."
            }
        }

        stage('Staging Integration Tests') {
            steps {
                echo "Performing integration tests in the staging environment."
            }
        }

        stage('Production Deployment') {
            steps {
                echo "Deploying the application to the production environment."
            }
        }
    }

    post {
        success {
            emailext attachLog: true,
            compressLog: true,
            to: 'virajprajapati14364@gmail.com',
            body: "The log is available at $JENKINS_HOME/jobs/$JOB_NAME/builds/lastSuccessfulBuild/log",
            subject: "Production Deployment Successful - Jenkins"
        }
        failure {
            emailext attachLog: true,
            compressLog: true,
            to: 'virajprajapati14364@gmail.com',
            body: "The log is available at $JENKINS_HOME/jobs/$JOB_NAME/builds/lastSuccessfulBuild/log",
            subject: "Production Deployment Failed - Jenkins"
        }
    }
}
