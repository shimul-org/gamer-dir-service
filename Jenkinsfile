pipeline {
	agent any
	stages {
  	stage('Docker Build') {
      steps {
      	sh 'docker build -t shimulsaha/gamer-dir-service:latest .'
      }
    }
    stage('Docker Push') {
      steps {
      	withCredentials([usernamePassword(credentialsId: 'my_docker_hub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
        	sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
          sh 'docker push shimulsaha/gamer-dir-service:latest'
        }
      }
    }
  }
}
