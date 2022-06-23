pipeline {
  agent any
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            echo 'hi'
          }
        }

        stage('readfile') {
          steps {
            httpRequest(url: 'http://urda:8080/job/RC-9.4/lastSuccessfulBuild/api/json?', acceptType: 'APPLICATION_JSON', contentType: 'APPLICATION_JSON', httpMode: 'GET', ignoreSslErrors: true, responseHandle: 'STRING', validResponseCodes: '200')
          }
        }

      }
    }

  }
}