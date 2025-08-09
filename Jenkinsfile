pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps { checkout scm }
    }
    stage('Build') {
      steps {
        sh 'mvn -v'
        sh 'mvn -B -DskipTests clean package'
      }
    }
    stage('Test') {
      steps { sh 'mvn -B test' }
    }
    stage('Archive') {
      steps {
        junit 'target/surefire-reports/*.xml'
        archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
      }
    }
  }
}

