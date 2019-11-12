#!groovy

// another trigger comment: Nov 12 @ 2:20pm
// another trigger comment: Nov 12 @ 1:13pm
// another trigger comment: Nov 12 @ 1:07pm
// another trigger comment: Nov 12 @ 1:00pm
// a simple pipeline
def pipeline = {
  node {
    stage('install') {
      def example = load "${rootDir}@script/Rambo.Groovy"
      sh 'echo installing'
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
