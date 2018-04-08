node {
  checkout scm

  /* Pull docker container from ECR */
  docker.withRegistry("https://225195660222.dkr.ecr.us-east-1.amazonaws.com/fugue/client", "ecr:us-east-1:ecsrepo" ) {
    docker.image("225195660222.dkr.ecr.us-east-1.amazonaws.com/fugue/client:latest").inside {
      withEnv(["AWS_DEFAULT_REGION=us-east-1"]) {
        withCredentials([string(credentialsId: 'FUGUE_USER_NAME', variable: 'FUGUE_USER_NAME'), 
                         string(credentialsId: 'FUGUE_USER_SECRET', variable: 'FUGUE_USER_SECRET')]) {
          sh "fugue status"
        }
      }
    }
  }
}
