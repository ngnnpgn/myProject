pipeline {
  agent { label 'linux' }
  tools {
    maven 'MAVEN3.5.2'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/effectivejenkins/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
