pipeline {
    agent any
    environment {
        POSTMAN_API_KEY = credentials("postman-api-key")
    }

    stages {

        stage('Verify Files') {
            steps {
                bat 'dir C:\\projects\\Restful-Booker-API-Testing'
            }
        }

        stage('postman CLI login') {
            steps {
                bat 'postman login --with-api-key %POSTMAN_API_KEY%'
            }
        }

        stage('Run newman Test') {
            steps {
                bat 'newman run "C:\\projects\\Restful-Booker-API-Testing\\New-Rest-Broker.postman_collection.json" --environment "C:\\projects\\Restful-Booker-API-Testing\\RestfulBooker.postman_environment.json" --reporters cli,htmlextra --reporter-htmlextra-export "newman\\newman-report.html"'
            }
        }

        stage('Archive HTML Report') {
            steps {
                archiveArtifacts artifacts: 'newman/newman-report.html', fingerprint: true
            }
        }
    }
}
