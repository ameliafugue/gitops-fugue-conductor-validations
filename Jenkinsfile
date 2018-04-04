pipeline {
  agent {
    docker.withRegistry("https://225195660222.dkr.ecr.us-east-1.amazonaws.com/fugue/client") {
      image 'fugue/client:latest'
      args '-v /var/run/docker.sock:/var/run/docker.sock'
    }
    
  }
  stages {
    stage('Stage One') {
      steps {
        sh 'fugue'
      }
    }
  }
}
