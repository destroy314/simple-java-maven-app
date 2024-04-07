pipeline {
    agent {
        docker {
            image 'maven:latest'
            args '--privileged -v /var/lib/jenkins/.m2:/.m2/'
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -e -B -DskipTests clean package' 
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
    }
}
