pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'hi'
        httpRequest(url: 'http://urda:8080/job/RC-9.5/lastSuccessfulBuild/api/json?tree=artifacts[fileName]', acceptType: 'APPLICATION_JSON', contentType: 'APPLICATION_JSON', ignoreSslErrors: true, httpMode: 'GET', validResponseCodes: '200', outputFile: 'succ.txt', responseHandle: 'STRING')
        sh 'echo cat \'succ.txt\' | grep -o \'(?<=Q-SYS Designer Installer).*?(?=.exe)\' '
      }
    }

  }
  environment {
    Designerfilename = ''
  }
}