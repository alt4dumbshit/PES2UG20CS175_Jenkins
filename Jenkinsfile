pipeline {
  agent {
    docker {
      image 'node:14'
      }
    }
    stages {
      stage('Clone repository') {
        steps {
          git branch: 'main',
          url: 'https://github.com/alt4dumbshit/PES2UG20CS175_Jenkins.git'
          }
        }
      stage('Install dependencies') {
        steps {
          sh 'npm install'
          }
        }
      stage('Build application') {
          steps {
            sh 'npm run build'
          }
        }
      stage('Test application') {
          steps {
            sh 'npm test'
          }
        }
      stage('Push Docker image') {
          steps {
            sh 'docker build -t jenkins/PES2UG20CS175:$11054c1bc8e849d88cb9d91d3a60c5d98ed9ef0cf380fbbf9d1806000a74ceed .'
            sh 'docker push jenkins/PES2UG20CS175:$11054c1bc8e849d88cb9d91d3a60c5d98ed9ef0cf380fbbf9d1806000a74ceed'
          }
        }
    }
}
