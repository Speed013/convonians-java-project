pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }        
        
        stage('Deploy to Tomcat server') {
            steps {
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'tomcatpassword', path: '', url: 'http://54.205.179.115:8080/')], contextPath: 'myapp', war: '**/*.war'
            }
        }
    }
}
