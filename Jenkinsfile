pipeline {
    agent any

    stages {
        stage('Setup') {
            steps {
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                npm run cy:run
            }
        }
        stage('Deploy') {
            steps {
                publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'D:\\Repositorio\\testes-e2e-ebac-shop\\cypress\\report\\mochawesome-report', reportFiles: 'mochawesome.html', reportName: 'EBAC Report', reportTitles: '', useWrapperFileDirectly: true])
            }
        }
    }
}