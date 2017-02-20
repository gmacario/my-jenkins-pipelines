pipeline {
  agent {
    docker {
      image 'gmacario/android-devenv:feat-rebase-appunite'
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

# install and setup android sdk
export ANDROID_HOME=/opt/android-sdk-linux
# accept licenses
mkdir -p "/opt/android-sdk-linux/licenses"
echo -e "\n8933bad161af4178b1185d1a37fbf41ea5269c55" > "/opt/android-sdk-linux/licenses/android-sdk-license"
echo -e "\n84831b9409646a918e30573bab4c9c91346d8abd" > "/opt/android-sdk-linux/licenses/android-sdk-preview-license"
echo -e "\nd975f751698a77b662f1254ddbeed3901e976f5a" > "/opt/android-sdk-linux/licenses/intel-android-extra-license"

./gradlew --help
./gradlew --stacktrace --no-daemon build 

./gradlew --info
./gradlew --stacktrace
#./gradlew

# EOF'''
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
