pipeline {
  agent any
  stages {
    stage('Test') {
      agent any
      steps {
        sh './gradlew clean test'
      }
    }

    stage('Publish Artifacts') {
      agent any
      steps {
        sh '''ls;
echo $MY_ENV'''
        archiveArtifacts(artifacts: 'build/test-results/*.xml', allowEmptyArchive: true)
      }
    }

  }
  environment {
    MY_ENV = 'hello'
  }
}