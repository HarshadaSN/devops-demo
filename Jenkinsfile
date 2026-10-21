pipeline {
  agent any
  environment {
    IMAGE = 'YOUR_DOCKERHUB_USER/devops-demo'
  }
  stages {
    stage('Docker Build') {
      steps {
        sh 'docker build -t $IMAGE:$BUILD_NUMBER -t $IMAGE:latest .'
      }
    }
    stage('Push') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'harshadasn', passwordVariable: 'Harshu@1997')]) {
          sh 'echo $DH_PASS | docker login -u $DH_USER --password-stdin'
          sh 'docker push $IMAGE:$BUILD_NUMBER'
          sh 'docker push $IMAGE:latest'
        }
      }
    }
  }
}