pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
                git 'git@github.com:nagoori/spring-framework-petclinic.git'
            }
        }
        stage('build') {
            steps {
                sh '/opt/maven38/bin/mvn clean package'
            }
        }
        stage('deploy') {
            steps {
                sh 'scp target/petclinic.war root@10.0.27.204:/opt/tomcat/webapps/'
            }
        }
    }
}
