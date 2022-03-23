node
{
    
 def mavenHome = tool name: "maven3.8.4"
 
 stage('CheckoutCode')
  {
  git branch: 'development', credentialsId: 'e6b869ff-b321-4cfb-a471-e125f6e8bc74', url: 'https://github.com/reddyanil8466/maven-web-application.git'  }

  stage('Build'){
  sh "${mavenHome}/bin/mvn clean package"
  }

  stage('ExecuteSonarQubeReport'){
  sh "${mavenHome}/bin/mvn clean sonar:sonar"
  }
  
  stage('UploadArtifactIntoNexus'){
  sh "${mavenHome}/bin/mvn clean deploy"
  }
 
  }
