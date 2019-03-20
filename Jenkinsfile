pipeline {
  agent any
  stages {
    stage('One') {
      parallel {
        stage('One') {
          steps {
            retry(count: 2) {
              sh 'java -version'
            }

            sh 'echo "Hello"'
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