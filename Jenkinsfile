node {

  checkout scm

  # Poll Git every minute
  #triggers { pollSCM('* * * * *') }

  # Pull docker container from ECR
  docker.withRegistry("https://225195660222.dkr.ecr.us-east-1.amazonaws.com/fugue/client", "ecr:us-east-1:ecsrepo" ) {
    image "fugue/client:latest"
  }

}
