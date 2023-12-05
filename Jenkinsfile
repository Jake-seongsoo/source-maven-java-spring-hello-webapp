pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage ("GetOS") {
            steps {
               sh 'cat /etc/os-release'
            }
        }
        stage ('Fetch'){
            steps{
                git branch:'main', url: 'https://github.com/Jake-seongsoo/source-maven-java-spring-hello-webapp.git'
            }
            post {
                success{
                    echo 'Fetch Success'
                }
            }
        }
    }
}
