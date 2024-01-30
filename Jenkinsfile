pipeline {
  agent none
  stages {
    stage('Maven Install') {
      agent {
        docker {
          image 'maven:3.9.5-eclipse-temurin-21-alpine'
        }
        steps {
          sh 'mvn clean install'
        }
      }
    }
  }
}
