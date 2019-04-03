pipeline {
  agent any
  environment {
        PATH = '/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/var/lib/snapd/snap/bin:/root/bin'
    }
  stages {
    stage('init') {
      steps {
        sh "draft config set registry $Registry"
        sh "draft init"
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
