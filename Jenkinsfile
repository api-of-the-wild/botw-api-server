#!groovy

pipeline {
  agent {
    docker { image "mhart/alpine-node:8"}
  }

  stages {
    stage('Build') {
      steps {
        sh 'node -v'
        sh 'npm -v'
        sh 'yarn -v'
        sh 'yarn install'
      }
    }
    
    stage('Lint') {
      steps {
        sh 'yarn test:lint'
      }
    }

    stage('Unit') {
      steps {
        sh 'yarn run test:unit'
      }
    }
  }
}