pipeline {

  agent any
  environment {
      PATH = "/usr/bin:$PATH"
  }
  stages {
      stage("git"){
          steps{
            git branch: 'main', url: 'https://github.com/vamsibyramla/sample.git'
          
          }
      }
      stage("build"){
          steps{
              sh "mvn clean package"
          }
      }
      stage("deploy"){
          steps{
              deploy adapters: [tomcat9(credentialsId: '4a4df800-f614-47e6-ae1c-27a024eaac0d', path: '', url: 'http://100.25.24.133:8080/')], contextPath: 'test', war: '**/*.war'
          }
      }
  }
}
