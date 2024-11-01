pipeline {
	agent any
	environment {
		NEW_VERSION = '1.0.0'
	}
	stages {
		stage("build") {
			steps {
				echo 'building the applicaiton...'
				echo "building version ${NEW_VERSION}"
			}
		}
		stage("test") {
			steps {
				echo 'testing the applicaiton...'
			}
		}
		stage("deploy") {
			steps {
				echo 'deploying the applicaiton...'
				withCredentials([[$class: 'UsernamePasswordMultiBinding',
					credentialsId: '519f293f-4286-443b-9e9b-b55bc1351b86', 
					usernameVariable: 'USER', 
					passwordVariable: 'PWD'
				]]) {
					sh 'printf ${USER}'
				}
			}
		}
	}
}