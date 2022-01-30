pipeline {
    agent any
    tools { 
        maven 'Maven 3.8.4'  
    }
    stages {
        stage('git repo & clean') {
            steps {
                //sh "rm -rf TicketBookingServiceJunitTesting"
                cleanWs()
                sh "git clone https://github.com/saurabh916/GitToJenkinsTestRepo.git"
                sh "mvn clean -f TicketBookingServiceJunitTesting"
            }
        }
        stage('install') {
            steps {
                sh "mvn install -f TicketBookingServiceJunitTesting"
            }
        }
        stage('test') {
            steps {
                sh "mvn test -f TicketBookingServiceJunitTesting"
            }
        }
        stage('package') {
            steps {
                sh "mvn package -f TicketBookingServiceJunitTesting"
            }
        }
    }
}
