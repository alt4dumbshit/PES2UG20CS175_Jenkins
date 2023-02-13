pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'build PES2UG20CS175-1'
        echo 'Build Stage Successful'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        echo 'Test Stage Successful'
        post {
          always {
            junit 'target/surefire-reports/*.xml'
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        sh 'mvn deploy'
        echo 'Deployment Successful'
      }
    }
  }
  post {
    failure {
      echo 'Pipeline Failed'
    }
  }
}
