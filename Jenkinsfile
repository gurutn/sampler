pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'hi'
        httpRequest(url: 'http://urda:8080/job/RC-9.5/lastSuccessfulBuild/api/json?tree=artifacts[fileName]', acceptType: 'APPLICATION_JSON', contentType: 'APPLICATION_JSON', ignoreSslErrors: true, httpMode: 'GET', validResponseCodes: '200', outputFile: 'succ.txt', responseHandle: 'STRING')
        readFile(file: 'succ.txt', encoding: 'UTF-8')
        pysh(script: 'der.py', returnStatus: true, returnStdout: true)
        sh 'echo cat \'succ.txt\' | grep -o -P \'(?<=Q-SYS Designer Installer).*?(?=.exe)\' '
      }
    }

  }
  environment {
    Designerfilename = ''
  }
}