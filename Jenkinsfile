pipeline {
  agent any                        // Run on any Jenkins worker

  tools {
    maven 'mvn-default'            // Use the Maven tool set up in Jenkins
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm               // Get code from the Git repo
      }
    }
    stage('Build') {
      steps {
        sh 'mvn -B clean package'   // Compile and package into a JAR
      }
    }
    stage('Test') {
      steps {
        sh 'mvn -B test'            // Run the unit tests
      }
    }
  }
}

