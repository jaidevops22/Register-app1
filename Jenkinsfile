pipelin {
  agent { label 'Jenkins-agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages{
    stage("Cleanup Workspace"){
             steps {
             cleanWs()
             }
    }

    stage("Checkout from SCM"){
            steps {
               git branch: 'main', credentailsId: 'github', url: "https://github.com/jaidevops22/Register-app1"
            }
    }
    stage("Build Application"){
      steps{
        sh "mvn clean package"
      }
    }

    stage("Test Application") {
      steps {
              sh "mvn test"
      }
    }
  }
}
