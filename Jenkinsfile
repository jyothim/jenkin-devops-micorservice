pipeline {
	//agent any
	agent {docker {image 'maven:latest'}}
	stages {
		stage ('Build') {
			steps {
				echo "Build"
			}

		}
		stage ('Test'){
			steps {
				echo "Test"
			}
		}
		stage ('Integration Test'){
			steps {
				echo "Integration Test"
			}
		}

	}
	post{
		always {
			echo "I alwyas run"
		}
		success {
			echo " I run on success"
		}
		failure {
			echo "I run on failure"
		}
	}
}
