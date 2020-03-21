pipeline {
  agent {
    docker {
      image 'maven:3.6-alpine'
      args '-u root -v /home/jenkins/mvnrepo:/root/.m2'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'mvn clean package fabric8:build fabric8:push -Dcheckstyle.skip=true -Pkubernetes -f kubernetes-hello-world-example/pom.xml'
      }
    }

  }
}
