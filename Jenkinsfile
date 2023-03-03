pipeline {
    agent any

    stages {
        stage('Git CLone') {
            steps {
                git url:'https://github.com/sai95573/project-2.git', branch: 'master'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }       
    }
}
