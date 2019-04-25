pipeline {
  agent {
        kubernetes {
          label 'nodejs-app-pod'
          yamlFile 'nodejs-pod.yaml'
        }
      }
  stages {
    stage('Test') {
      steps {
        sh 'java -version'
        container('nodejs') {
          echo 'Hello!'   
          sh 'node --version'
        }
      }
    }
    stage('Build and Push Image') {
      when {
         beforeAgent true
         branch 'master'
      }
      steps {
         echo "TODO - build and push image"
      }
    }
  }
}
