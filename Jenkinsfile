node {
      currentBuild.result = "SUCCESS"
	deleteDir()
	try { 
		stage('Clone') {
		checkout scm
          }
		stage('Build') {
		sh "echo 'shell scripts to run the build'"
          }
		stage('Parallel Test') {
                  parallel 'static': {
                },
                'unit': {
                   sh "echo 'shell scripts to run the unit tests'"
                },
                'integration': {
                   sh "echo 'shell scripts to run the integration tests'"
                },
                'code-quality': {
                   sh "echo 'shell scripts to run the code-quality tests'"
                },
                'performance': {
                   sh "echo 'shell scripts to run the performance tests'"
                },
                'acceptance': {
                   sh "echo 'shell scripts to run the acceptance tests'"
                }
          }
		stage('Create MR') {
		sh "echo 'create MR to Merge Code'"
          }
		stage('Deploy') {
		sh "echo 'shell scripts to Deploy Code'"
          }

    } catch(err) {
      currentBuild.result = "FAILED"
      throw err

      }
}
