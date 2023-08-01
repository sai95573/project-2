pipeline {
  agent any
  stages {
    stage ('Git Clone') {
        git url:'https://github.com/sai95573/project-2.git', branch: 'master'
        }  
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat9(credentialsId: 'tomcat-id', path: '', url: 'http://ec2-65-1-2-222.ap-south-1.compute.amazonaws.com:8080')], contextPath: '/pipeline', onFailure: false, war: '**/*.war' 
        }
      }
    }
  }
}
