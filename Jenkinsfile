pipeline {
  agent none
  stages {
    stage('build') {
      steps {
        echo 'hi'
        httpRequest(url: 'http://urda:8080/job/RC-9.4/lastSuccessfulBuild/api/json?', acceptType: 'APPLICATION_JSON', contentType: 'APPLICATION_JSON', ignoreSslErrors: true, httpMode: 'GET', validResponseCodes: '200')
      }
    }

  }
}