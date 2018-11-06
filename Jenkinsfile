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
		stage('Tests') {
                     parallel 'static': {
                },
                'unit':{
		sh "echo 'shell scripts to run the build'"
                }
          }

    } catch(err) {
      currentBuild.result = "FAILED"
      throw err

      }
}
