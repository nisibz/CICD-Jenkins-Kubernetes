pipeline {
    agent any

    stages {
        stage('Build and Push Docker Image') {
            steps {
                script {
                    env.VERSION = "0.0.${BUILD_NUMBER}"
                    sh('''
                        sudo docker build -t nisibz/cicd-jenkins-kubernetes:${VERSION} .
                        sudo docker push nisibz/cicd-jenkins-kubernetes:${VERSION}
                    ''')
                }
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                script {
                    withKubeConfig(credentialsId: 'kubeconfig') {
                        sh (
                            '''
                            cat kubernetes/deployment.yml | envsubst | kubectl apply -f -
                            kubectl apply -f kubernetes/service.yml
                            '''
                        )
                    }
                }
            }
        }
    }
}
