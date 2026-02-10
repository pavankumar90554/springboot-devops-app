pipeline {
  agent any

  tools {
    maven 'Maven'
    jdk 'java17'
  }

  stages {

    stage('Checkout Code') {
      steps {
        git 'https://github.com/pavankumar90554/springboot-devops-app.git'
      }
    }

    stage('Build with Maven') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t springboot-devops-app: .'
      }
    }
  }
}

cat <<EOF > Jenkinsfile
pipeline {
  agent any

  tools {
    maven 'Maven'
    jdk 'java17'
  }

  stages {

    stage('Checkout Code') {
      steps {
        git 'https://github.com/pavankumar90554/springboot-devops-app.git'
      }
    }

    stage('Build with Maven') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build -t springboot-devops-app: .'
      }
    }
  }
}

