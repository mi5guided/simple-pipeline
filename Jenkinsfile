#!groovy

// a simple pipeline
def pipeline = {
  node ('single') {
    stage('install') {
      sh 'echo install'
    }

    stage('build') {
      sh 'echo build'
    }

    stage('test'){
      sh 'echo test'
    }
    
    stage('deploy') {
      sh 'echo deploy'
    }
  }
}

pipeline()
