pipeline {
    agent any

    stages {
        stage('Setup') {
            steps {
                powershell 'npm install'
            }
        }
        stage('Test') {
            steps {
                powershell 'npm run cy:run'
            }
        }
        stage('Deploy') {
            steps {
                publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'mochawesome-report', reportFiles: 'mochawesome.html', reportName: 'EBAC Report', reportTitles: '', useWrapperFileDirectly: true])
            }
        }
    }
}