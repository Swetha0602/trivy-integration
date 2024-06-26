pipeline {
    agent any
    environment {
        GITHUB_CREDS=credentials('Github_creds')
        IMAGE_NAME='sriswetha06/pipeline-image'
        IMAGE_VERSION='v1'
        DOCKERHUB_CREDS=credentials('dockerhub-creds')
    }
    stages {
      stage('Trivy Version') {
        steps {
                sh 'trivy --version'
              }
         }
       stage('Docker Login'){
            steps{
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                      sh "docker login -u $USERNAME -p $PASSWORD"
                }
            }
        }
        stage('Trivy Scan') {
            steps {
                sh 'trivy image $IMAGE_NAME:$IMAGE_VERSION'
            }
        }
    }
}
