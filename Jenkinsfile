pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('Testing') {
      steps {
        sh 'mvn clean'
        sh 'mvn test'
      }
    }

  
  stage('Whatever')  {
    steps  {
      sh 'echo "Hello world Jenkins!"'
    }
  }
}
  post {
  always {
    junit 'biojava-alignment/target/surefire-reports/**/*.xml'
  }
}
}
