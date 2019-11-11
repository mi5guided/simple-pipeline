#!groovy

// a simple pipeline
def pipeline = {
	node ('single') {
		stage('install')
			echo "install"
		stage('build')
			echo "build"
		stage('test')
			echo "test"
		stage('deploy')
			echo "deploy"
  }
}

pipeline()
