pipeline {
  agent any
  stages {
    stage('init') {
      steps {
        sh "/usr/local/bin/draft init"
      }
    }
    stage('Draft create') {
      steps {
        sh "echo Created Dockerfile"
        sh "/usr/local/bin/draft create"
      }
    }
    stage('Draft up') {
      steps {
        sh "echo Created Dockerfile"
        sh "/usr/local/bin/draft up"
      }
    }
  }
}
