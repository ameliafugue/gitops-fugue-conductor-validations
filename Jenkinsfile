node {

  /* Setup our environment */
  withEnv(["AWS_DEFAULT_REGION=us-east-1"]) {

    /* Checkout git repo */
    checkout(scm)

    /* Use Amazon ECR repo */
    docker.withRegistry("https://225195660222.dkr.ecr.us-east-1.amazonaws.com/fugue/client", "ecr:us-east-1:ecsrepo" ) {

      /* Pull the fugue client docker container from ECR */
      docker.image("225195660222.dkr.ecr.us-east-1.amazonaws.com/fugue/client:latest").inside {

        /* Set our Fugue credentials */
        withCredentials([string(credentialsId: "FUGUE_USER_NAME", variable: "FUGUE_USER_NAME"),
                         string(credentialsId: "FUGUE_USER_SECRET", variable: "FUGUE_USER_SECRET")]) {

          /* Apply policy to the Fugue Conductor */
          def cmdStatusCode = sh(script: "fugue policy validation-remove BestPractices -y", returnStatus: true)
          if(cmdStatusCode == 0) {
            sh(script: "fugue policy validation-add Policy/BestPractices.lw --name BestPractices", returnStatus: true)
          } else {
            sh(script: "fugue policy validation-add Policy/BestPractices.lw --name BestPractices", returnStatus: true)
          }
        }
      }
    }
  }
}
