pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        git(url: 'https://github.com/Krishna1025/sample-java-project.git', branch: 'master')
      }
    }
    stage('compile') {
      parallel {
        stage('compile') {
          steps {
            bat 'mvn compile'
          }
        }
        stage('build') {
          steps {
            bat 'mvn package'
          }
        }
      }
    }
    stage('deploy to artifact') {
      steps {
        archiveArtifacts 'test'
        bat 'mvn deploy'
      }
    }
  }
}