node {
  // Mark the code checkout 'stage'....
  stage('Stage Checkout') {
   
    // Checkout code from repository and update any submodules
    checkout scm
    sh 'git submodule update --init' 
  }

  stage('Build image') {
     /* This builds the actual image; synonymous to
      * docker build on the command line */
     //branch name from Jenkins environment variables
     echo "My branch is: ${env.BRANCH_NAME}"
     app = docker.build("guillelucero/invoiceninja")
  }

  stage('Push image') {
     /* Finally, we'll push the image with two tags:
      * First, the incremental build number from Jenkins
      * Second, the 'latest' tag.
      * Pushing multiple tags is cheap, as all the layers are reused. */
     docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
        app.push("${env.BUILD_NUMBER}")
     //   app.push("latest")
     }
  }

}
