pipeline {
    agent { label 'Jenkins-Agent' }
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
                    git branch: 'main', credentialsId: 'github', url: 'https://github.com/jaidevops22/Register-app1.git'
                }
        }

        stage("Build Application"){
            steps {
                sh "mvn package"
            }
     }

     stage("Test Application"){
           steps {
                 sh "mvn test"
           }
    }
  }
}
