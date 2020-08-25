pipeline {
   agent any

    stages{
        stage('Build Docker Image'){
        steps{
        sh "docker build . -t gzlkhan/furiouswheel:${env.BUILD_ID}"
     }
}

        stage('Dockerhub Push'){

        steps{
        withCredentials([string(credentialsId: 'docker-hub', variable: 'dockerHubPwd')]) {
        sh "docker login -u gzlkhan -p ${dockerHubPwd}"
        sh "docker push gzlkhan/furiouswheel:${env.BUILD_ID}"
        }
     }
   }

}

}
