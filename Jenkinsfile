pipeline {
  agent any
  stages {
    stage('Test') {
      steps {
        sh './gradlew clean test'
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