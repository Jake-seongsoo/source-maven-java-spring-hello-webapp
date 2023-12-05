pipeline {
  agent any

  triggers {
    pollSCM('* * * * *')
  }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', 
        url: 'https://github.com/Jake-seongsoo/source-maven-java-spring-hello-webapp.git'
      }
    }
    stage('Build') {
      steps {
        sh "mvn package -f pom.xml"
      }
    }
    stage('Test') {
      steps {
        echo "Test is done"
      }
    }
    stage('Deploy') {
      steps {
        deploy adapters: [tomcat9(credentialsId: 'tomcat-manager', url: 'http://3.36.13.174:8080/')], contextPath: null, war: 'target/hello-world.war'
      }
    }
  }
}
