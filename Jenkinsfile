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
