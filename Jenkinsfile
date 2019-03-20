pipeline {
  agent any
  stages {
    stage('One') {
      parallel {
        stage('One') {
          steps {
            sh 'echo "Hello"'
            retry(count: 2)
          }
        }
        stage('OneSec') {
          steps {
            isUnix()
            echo 'This is a parallel stage'
          }
        }
      }
    }
    stage('Two') {
      steps {
        libraryResource 'myfile'
      }
    }
  }
}