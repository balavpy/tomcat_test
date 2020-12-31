pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn clean install package'
      }
    }

    stage('Build Archive') {
      steps {
        archiveArtifacts(fingerprint: true, artifacts: 'webapp/target/*.war')
      }
    }

    stage('Copy') {
      steps {
        copyArtifacts(projectName: 'Node1-TestJob', fingerprintArtifacts: true, target: 'target/')
      }
    }

  }
}