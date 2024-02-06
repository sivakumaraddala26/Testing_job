pipeline {
 environment {
 imagename = "ubuntu_image"
 registryCredential = 'sivakumaraddala'
 dockerImage = ''
 }
 agent any
 stages {
 stage('Cloning Git') {
 steps {
 git([url: 'https://github.com/sivakumaraddala26/Testing_job.git', branch: 'master'])
 }
 }
 stage('Building image') {
 steps{
 script {
 dockerImage = docker.build imagename
 }
 }
 }
        stage('Trivy Scan') {
            steps {
                // Run Trivy scan on the Docker image
                sh 'trivy --exit-code 1 ${dockerImage}'
            }
        }
 stage('Running image') {
 steps{
 script {
 sh "docker run ${imagename}:latest"
 }
 }
 }
 // stage('Deploy Image') {
 // steps{
 // script {
 // docker.withRegistry( 'https://index.docker.io/v1/', registryCredential ) {
 // dockerImage.push("$BUILD_NUMBER")
 // dockerImage.push('latest')
 // }
 // }
 // }
 // }
 }
}
