pipeline {
  agent { label 'master' }
  tools {
    maven 'M3'
  }
  stages {
    stage('checkout') {
      steps {
        git credentialsId: 'github_user', url: 'https://github.com/devopsjan2021/myProjecjava.git'
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
