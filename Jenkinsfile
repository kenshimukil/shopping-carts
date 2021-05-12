pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'this is the build job'
        sh 'mvn compile'
      }
    }

    stage('two') {
      steps {
        echo 'this is the test job'
        sh 'mvn test'
      }
    }

    stage('three') {
      steps {
        echo 'this is the package job'
        sh 'mvn package'
      }
    }

    stage('archive') {
      steps {
        archiveArtifacts '**/target/*.jar'
      }
    }

  }
  tools {
    maven 'maven'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}