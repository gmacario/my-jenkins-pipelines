pipeline {
  agent {
    docker {
      image 'gmacario/android-devenv:latest'
    }
  }
  stages {
    stage('Checkout') {
      steps {
        sh 'pwd'
        git 'https://github.com/gmacario/colorcode'
        pwd()
        sh 'ls -la'
      }
    }
    stage('Build') {
      steps {
        echo 'hello'
        sh '''#!/bin/bash -xe

# DEBUG
id
pwd
ls -la
printenv | sort

# Configure git
git config --global user.name "easy-jenkins"
git config --global user.email "$(whoami)@$(hostname)"

export JAVA_HOME=
chmod a+x gradlew

./gradlew --help
./gradlew --stacktrace --no-daemon build 

# ./gradlew --info
# ./gradlew --stacktrace
# ./gradlew

# Build a debug APK
# See https://developer.android.com/studio/build/building-cmdline.html#DebugMode
./gradlew assembleDebug

# EOF
'''
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Chrome": {
            echo 'TODO: Testing in Chrome'       
          },
          "Firefox": {
            echo 'TODO: Testing in Firefox'
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        echo 'TODO: Deploying'
        sh 'pwd'
        sh 'ls -la'
        sh 'ls -la build/'
        sh 'ls -la build/generated/'
      }
    }
  }
  post {
    always {
       archive 'build/generated/**/*.apk'
       // junit 'build/reports/**/*.xml'
    }
  }
}
