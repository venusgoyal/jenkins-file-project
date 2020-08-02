pipeline {
  agent { label 'master' }
  tools {
    maven 'maven-3.6.3'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/venusgoyal/jenkins-file-project.git'
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
