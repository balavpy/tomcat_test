pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn clean test install package'
      }
    }

    stage('Build Archive') {
      steps {
        archiveArtifacts(fingerprint: true, artifacts: 'webapp/target/*.war')
      }
    }

    stage('Testing') {
      steps {
        realtimeJUnit(testResults: 'target/*.xml')
      }
    }

  }
}