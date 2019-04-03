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
            withCredentials([usernamePassword(credentialsId: 'docker-hub', usernameVariable: 'ajayr5', passwordVariable: '78Q6wa3s0%')]) {
                sh "echo Starting pod"
                sh "draft up"
            }
        }
  }
