pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        echo 'hi'
        httpRequest(url: 'http://urda:8080/job/RC-9.5/lastSuccessfulBuild/api/json?tree=artifacts%5BfileName%5D', acceptType: 'APPLICATION_JSON', contentType: 'APPLICATION_JSON', ignoreSslErrors: true, httpMode: 'GET', validResponseCodes: '200', outputFile: 'succ.txt', responseHandle: 'STRING')
        sh '''value=`cat succ.txt`
echo "$value"'''
        copyArtifacts(projectName: 'test job', target: 'C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\sampler_main', filter: 'software/Installers/Q-Sys%20Designer/Release/Web/', parameters: 'http://localhost:8080/job/test%20job/lastSuccessfulBuild/artifact/')
      }
    }

  }
  environment {
    Designerfilename = ''
  }
}