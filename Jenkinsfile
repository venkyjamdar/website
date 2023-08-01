<<<<<<< HEAD
pipeline{
  agent any
  stages{
    stage("1.CodeClone"){
      steps{
        git credentialsId: 'github-Cred', url: 'https://github.com/ommaxyl/website.git'
      }
=======
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Job1: Build
                git branch: ' ', url: 'https://github.com/ommaxyl/wbsite'
                sh 'docker build -t myfile /var/www/html'
            }
        }
        stage('Test') {
            when {
                anyOf {
                    branch 'master'
                    branch 'develop'
                }
            }
            steps {
                // Job2: Test
                sh 'docker run your-image-name npm test'
            }
        }
        stage('Deploy to Prod') {
            when {
                branch 'master'
            }
            steps {
                // Job3: Prod
                sh 'docker push your-image-name'
                // Add additional steps to deploy to production if needed
            }
        }
>>>>>>> master
    }
    stage("2.Build"){
      steps{
        sh "sudo docker build /home/ubuntu/jenkins/workspace/Job1 -t job1"
        sh "sudo docker tag job1 ommaxyl/job1"
      }
    }
    stage("3.Push Built to DockerHub"){
        steps{
            withCredentials([string(credentialsId: 'dockerHub', variable: 'dockerHub')]) {
             sh "sudo docker login -u ommaxyl -p ${dockerHub}"
        }
             sh "sudo docker push ommaxyl/job1"    
      }
    }
  }
}
