pipeline {
	agent any
	//agent {docker {image 'maven:latest'}}
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH ="$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages {
		stage ('Checkout') {
			steps {
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage ('Compile'){
			steps {
				sh "mvn clean compile"
			}
		}
		stage ('Test'){
			steps {
				sh "mvn test"
			}
		}
		stage ('Integration Test'){
			steps {
				sh "mvn failesafe: integration-test failesafe: verify"
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
