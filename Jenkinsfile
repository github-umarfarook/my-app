pipeline {
    agent any
    tools {
        Maven "Maven"
    }
    stages {
        stage('---clean---') {
            steps {
                sh "mvn clean"
            }
        }
        stage('--test--') {
            steps {
                sh "mvn test"
            }
        }
        stage('--package--') {
            steps {
                sh "mvn package"
            }
        }
        stage('--install--') {
            steps {
                sh "mvn install"
            }
        }    
    }
}
