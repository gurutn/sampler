pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'hi'
        httpRequest(url: 'http://urda:8080/job/RC-9.4/lastSuccessfulBuild/api/json?', acceptType: 'APPLICATION_JSON', contentType: 'APPLICATION_JSON', ignoreSslErrors: true, httpMode: 'GET', validResponseCodes: '200', outputFile: 'succ.txt', responseHandle: 'STRING')
        readFile(file: 'succ.txt', encoding: 'text')
      }
    }

  }
}