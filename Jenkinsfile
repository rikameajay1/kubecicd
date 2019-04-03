pipeline {
  agent any
  environment {
        PATH = '/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/var/lib/snapd/snap/bin:/root/bin'
        KUBECONFIG = '/etc/kubernetes/admin.conf'
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
        sh "draft create"
      }
    }
    stage('Draft up') {
        withDockerRegistry(credentialsId: 'docker-hub', url: 'docker.io/ajayr5') {
        sh "echo Starting pod"
        sh "draft up"
      }
    }
  }
}
