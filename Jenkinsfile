pipeline{
  environment{
    reg="1008yash/poepart2"
    regCre = "yashzipoe"
    dockerImg = ""
  }
  agent any
  stages{
    stage('Build Image'){
      steps{
        script{
          dockerImg = docker.build reg + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Deploy the image'){
      steps{
        script{
          docker.withRegistry('',regCre){
            dockerImg.push()
          }
        }
      }
    }
  }
}
