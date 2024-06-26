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
    }
}
