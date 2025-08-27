pipeline {
  agent {
    docker {
      image 'maven:3.9-eclipse-temurin-17'
      args '-u root:root'
    }
  }
  triggers {
    // comenta esto si luego usas webhook
    pollSCM('H/2 * * * *')
  }
  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
    stage('Build') {
      steps {
        sh 'mvn -q -DskipTests package'
      }
    }
    stage('Run') {
      steps {
        sh 'java -cp target/jenkins-ci-practice-1.0-SNAPSHOT.jar com.example.App'
      }
    }
  }
  post {
    always {
      archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
    }
  }
}
