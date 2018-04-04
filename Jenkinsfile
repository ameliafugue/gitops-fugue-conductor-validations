pipeline {
  docker.withRegistry("https://225195660222.dkr.ecr.us-east-1.amazonaws.com/fugue/client", "ecr:us-east-1:ecsrepo" ) {
    image "fugue/client:latest"
  }
  stages {
    stage("Stage One") {
      steps {
        sh "fugue"
      }
    }
  }
}
