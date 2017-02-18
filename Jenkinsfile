pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        echo 'hello'
        git(url: 'https://github.com/gmacario/genivi-dev-platform', branch: 'master', changelog: true)
      }
    }
    stage('Build') {
      steps {
        echo 'hello'
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Chrome": {
            echo 'testing in chrome'
            
          },
          "Firefox": {
            echo 'testing in firefox'
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploying'
      }
    }
  }
}
