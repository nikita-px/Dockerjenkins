pipeline{
  agent any
  stages{
    stage('Cheheckour'){
      steps{
        git url :'https://github.com/nikita-px/Dockerjenkins.git',branch:'main'
      }
    }
    stage('Build Image'){
      steps{
        bat 'docker build -t mywebsite.'

      }
    }
    stage('Stp old containers'){
      steps{
        bat 'docker stop mycont || exit 0'
        bat 'docker rm mycont || exit 0'
      }
    }
    stage('Rum my image- containers'){
      step{
        bat 'docker run -d -p 7000:80 --name mycont mywebsite'
      }
    }
  }
}
