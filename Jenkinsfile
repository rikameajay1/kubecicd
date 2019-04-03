pipeline {
  agent any
  stages {
    stage('Draft init') {
      steps {
        sh "/usr/local/bin/draft init"
      }
    }
    stage('Draft create') {
      steps {
        sh "/usr/local/bin/draft create"
      }
    }
  }
}
