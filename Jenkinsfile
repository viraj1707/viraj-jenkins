pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Retrieving source code from the directory specified by the environment variable."
                echo "Compiling the code and creating necessary artifacts."
                echo "Done"
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Executing unit tests."
                echo "Executing integration tests."
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Evaluating code quality using a code analysis tool."
            }
        }
        stage('Security Scan') {
            steps {
                echo "Detecting vulnerabilities using a security scanning tool."
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Conducting integration tests in the staging environment."
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Releasing the code to the production environment."
            }
        }
    }
    post {
        success {
            emailext(
                attachLog: true,
                compressLog: true,
                to: 'virajprajapati14364@gmail.com',
                body: "The log is available at \$JENKINS_HOME/jobs/\$JOB_NAME/builds/lastSuccessfulBuild/log",
                subject: 'Production Deployment Successful - Jenkins'
            )
        }
        failure {
            emailext(
                attachLog: true,
                compressLog: true,
                to: 'virajprajapati14364@gmail.com',
                body: "The log is available at \$JENKINS_HOME/jobs/\$JOB_NAME/builds/lastSuccessfulBuild/log",
                subject: "Production Deployment Failed - Jenkins"
            )
        }
    }
}
