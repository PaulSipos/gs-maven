pipeline {
  agent any

  options {
    buildDiscarder (logRotator(numToKeepStr: '10' , artifactNumToKeepStr: '2'))
  }
  stages {
    stage ('Build') {
      steps {
        sh 'ant -f build.xml -v'
      }
    }
  }

  post {
    always {
      archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
    }
  }
}
