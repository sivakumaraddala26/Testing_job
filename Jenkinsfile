pipeline {
 environment {
 imagename = "sivakumaraddala26/my-image"
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
        //  stage('Build and Push Docker Image') {
        //     steps {
        //         script {
        //             docker.withRegistry('https://hub.docker.com/', registryCredential) {
        //                 def customImage = docker.build('')
        //                 customImage.push()
        //             }
        //         }
        //     }
        // }
 stage('Building image') {
 steps{
 script {
 dockerImage = docker.build imagename
 }
 }
 }
 // stage('Running image') {
 // steps{
 // script {
 // sh "docker run ${imagename}:latest"
 // }
 // }
 // }
 // stage('Deploy Image') {
 // steps{
 // script {
 // docker.withRegistry( '', registryCredential ) {
 // dockerImage.push("$BUILD_NUMBER")
 // dockerImage.push('latest')
 // }
 // }
 // }
 // }
 }
}
