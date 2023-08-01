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
        stage ('Deploy') {
          steps {
	    sshagent(['deployuser']) {
	        sh "scp -o StrictHostKeyChecking=no target/sample-2.war ubuntu@65.1.2.222/var/lib/tomcat9/webapps/webapptest.war"
	        }
	    }
          }    
        }
}
