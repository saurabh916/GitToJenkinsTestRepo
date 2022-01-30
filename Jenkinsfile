pipeline {
    agent any
    tools { 
      maven 'MAVEN_HOME' 
      jdk 'JAVA_HOME' 
    }
    stages {
        stage('git repo & clean') {
            steps {
                //sh "rm -rf TicketBookingServiceJunitTesting"
                cleanWs()
                sh "git clone https://github.com/saurabh916/GitToJenkinsTestRepo.git"
                sh "mvn clean -f GitToJenkinsTestRepo"
            }
        }
        stage('install') {
            steps {
                sh "mvn install -f GitToJenkinsTestRepo"
            }
        }
        stage('test') {
            steps {
                sh "mvn test -f GitToJenkinsTestRepo"
            }
        }
        stage('package') {
            steps {
                sh "mvn package -f TGitToJenkinsTestRepo"
            }
        }
    }
}
