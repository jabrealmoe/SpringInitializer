pipeline {
 agent none
	stages {
	     stage('Run Tests') {
	     parallel {
	         stage('Test On Windows') {
	             steps {
			sh 'echo Hello Windows'
		     }
	         }
	     }
	     }
	     stage('Run Tests') {
	     parallel {
	         stage('Test On Windows') {
	             steps {
			sh 'echo Hello Windows'
		     }
	         }
	     }
	     }
	}
}
