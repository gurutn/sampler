pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'hi'
        httpRequest(url: 'http://urda:8080/job/RC-9.5/lastSuccessfulBuild/api/json?tree=artifacts%5BfileName%5D', acceptType: 'APPLICATION_JSON', contentType: 'APPLICATION_JSON', ignoreSslErrors: true, httpMode: 'GET', validResponseCodes: '200', outputFile: 'succ.txt', responseHandle: 'STRING')
        fileExists 'succ.txt'
        sh 'cat cat \'C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\sampler_main\\succ.txt\' | grep "Designer\\/Release\\/Web\\/"'
        echo 'result'
      }
    }

  }
  environment {
    Designerfilename = ''
  }
}