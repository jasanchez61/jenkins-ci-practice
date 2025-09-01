pipeline {
  agent {
    docker {
      image 'maven:3.9-eclipse-temurin-17'
      args '-u root:root'
    }
  }
  stages {
    stage('Checkout'){ steps { checkout scm } }
    stage('Build'){ steps { sh 'mvn -q -DskipTests package' } }
    stage('Run'){ steps { sh 'java -cp target/jenkins-ci-practice-1.0-SNAPSHOT.jar com.example.App' } }
  }
}
