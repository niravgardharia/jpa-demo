pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh 'sh \'mvn compile\''
      }
    }

    stage('Test') {
      steps {
        sh 'sh \'mvn test\''
      }
    }

    stage('Package') {
      steps {
        sh 'sh \'mvn package\''
      }
    }

    stage('Archive Artifact') {
      steps {
        archiveArtifacts(artifacts: 'target/*.jar', allowEmptyArchive: true)
      }
    }

    stage('Result') {
      steps {
        junit '**/*.xml'
      }
    }

  }
}