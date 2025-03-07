pipeline {
	agent any
	//agent {docker {image 'maven:latest'}}
	stages {
		stage ('Build') {
			steps {
				//sh 'mvn --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
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
