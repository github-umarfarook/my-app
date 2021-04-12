pipeline {
    agent any
    tools {
       maven "Maven"
    }
    stages {
        stage('----clean----') {
            steps {
                sh " rm -rf /var/lib/jenkins/workspace/*"
                sh "mvn clean"
            }
        }
        stage('---test---') {
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
        stage('--Deploy--') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat_user', path: '', url: 'http://54.163.36.240:8080/')], contextPath: null, onFailure: false, war: '**/*.war'
            }
        }    
    }
}
