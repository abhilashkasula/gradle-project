pipeline {
  agent any
  stages {
    stage('Test') {
      environment {
        MY_ENV = 'hello'
      }
      parallel {
        stage('Test') {
          steps {
            sh './gradlew clean test'
          }
        }

        stage('Build') {
          steps {
            sh './gradlew clean build -x test'
          }
        }

      }
    }

    stage('Publish Artifacts') {
      steps {
        sh 'echo $MY_ENV'
        archiveArtifacts(artifacts: 'build/test-results/*.xml', allowEmptyArchive: true)
      }
    }

  }
}