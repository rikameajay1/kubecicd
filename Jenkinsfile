env.PATH = '/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/var/lib/snapd/snap/bin:/root/bin'
env.KUBECONFIG = '/etc/kubernetes/admin.conf'
node {
         stage('init') {
            sh "draft config set registry $Registry"
            sh "draft init"
        }
        
        stage('Draft create') {
            sh "echo Created Dockerfile"
            sh "draft create"
        }
 				
        stage('Draft up') {
            withDockerRegistry(credentialsId: 'docker-hub', url: 'docker.io/ajayr5') {
                sh "echo Starting pod"
                sh "draft up"
            }
        }
  }
