pipeline {
    agent {
        docker {
            image 'maven:latest' 
            args '-v /var/lib/jenkins/.m2:/root/.m2'
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
