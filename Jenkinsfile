pipeline {
  agent any

  environment {
    IMAGE_NAME = "pavankumar213/springboot-devops-app"
  }

  stages {

    stage('Checkout') {
      steps {
        git 'https://github.com/pavankumar90554/springboot-devops-app.git'
      }
    }

    stage('Build App') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('Build & Push Docker Image') {
      steps {
        sh '''
          docker build -t $IMAGE_NAME:$BUILD_NUMBER .
          docker push $IMAGE_NAME:$BUILD_NUMBER
        '''
      }
    }

    stage('Deploy to Kubernetes') {
      steps {
        sh '''
          sed -i "s/BUILD_NUMBER/$BUILD_NUMBER/g" deployment.yaml
          kubectl apply -f deployment.yaml
       '''
      }
    }
  }
}
