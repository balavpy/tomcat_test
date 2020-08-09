pipeline {
	agent any
	tools {
        maven 'Maven 3.6.3'
        jdk 'jdk8'
    }
	stages {
		stage ('Initialize') {
			steps {
				sh '''
					echo "PATH = ${PATH}"
					echo "M2_HOME = ${M2_HOME}"
				'''
			}
		}
		stage('build') {
			steps {
				mvn clean install package
			}
			post {
				success {
					echo "success build"
				}
			}
		}
	
}
