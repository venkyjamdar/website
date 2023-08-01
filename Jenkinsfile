pipeline{
  agent any
  stages{
    stage("1.CodeClone"){
      steps{
        git credentialsId: 'github-Cred', url: 'https://github.com/ommaxyl/website.git'
      }
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
