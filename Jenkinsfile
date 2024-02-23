pipeline {
    agent any

    stages {
        stage('Get Nodes') {
            steps {
                script {
                    withKubeConfig(credentialsId: 'kubeconfig') {
                        sh (
                            '''
                            kubectl get nodes
                            '''
                        )
                    }
                }
            }
        }
    }
}
