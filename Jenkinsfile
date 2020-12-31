pipeline {
  agent any
  stages {
    stage('Test') {
      agent any
      steps {
        sh './gradlew clean test'
      }
      post {
        always {
          publishHTML([allowMissing: true, alwaysLinkToLastBuild: true, keepAll: true, reportDir: 'build/reports/tests/test', reportFiles: 'index.html', reportName: 'Test HTML Report', reportTitles: 'report'])
        }
      }
    }
  }
  environment {
    MY_ENV = 'hello'
  }
}
