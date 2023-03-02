pipeline {
  agent any
  stages {
    stage ('Git Clone') {
        git credentialsId: 'github-cred', url: 'https://github.com/sai95573/project-2.git'
        }  
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
  }
}
