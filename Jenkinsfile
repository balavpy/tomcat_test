pipeline {
	agent any
	stages {
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
