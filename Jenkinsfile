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
    }
}
