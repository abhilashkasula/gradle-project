pipeline {
  agent {
    docker {
      image 'alpine:latest'
    }

  }
  stages {
    stage('Test') {
      agent {
        docker {
          image 'alpine:latest'
        }

      }
      environment {
        MY_ENV = 'hello'
      }
      steps {
        sh './gradlew clean test'
      }
    }

    stage('Publish Artifacts') {
      agent any
      steps {
        sh '''ls;
echo MY_ENV'''
        archiveArtifacts(artifacts: 'build/test-results/*.xml', allowEmptyArchive: true)
      }
    }

  }
}