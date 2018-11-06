node {
      currentBuild.result = "SUCCESS"
	deleteDir()
	try { 
		stage('Clone') {
                    when {
                       expression {
                            GIT_BRANCH = 'origin/' + sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
                            return !(GIT_BRANCH == 'origin/master' || params.FORCE_FULL_BUILD)
               }

            }
		checkout scm
          }
		stage('Build') {
		sh "echo 'shell scripts to run the build'"
          }
		stage('Create MR') {
		sh "echo 'create MR to Merge Code'"
          }
		stage('Tests') {
                 parallel 'static': {
                },
                'unit': {
                   sh "echo 'shell scripts to run the unit tests'"
                },
                'integration': {
                   sh "echo 'shell scripts to run the integration tests'"
                }
          }
		stage('Deploy') {
		sh "echo 'shell scripts to Deploy Code'"
          }
    } catch(err) {
      currentBuild.result = "FAILED"
      throw err

      }
}
