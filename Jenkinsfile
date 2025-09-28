pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }

    stage('Build') {
      steps {
        // create a tiny artifact (HTML) so we can archive it
        sh '''
          mkdir -p build
          echo "<!doctype html><html><body><h1>Hello from Jenkins!</h1><p>Commit: ${GIT_COMMIT}</p></body></html>" > build/index.html
        '''
      }
    }

    stage('Test') {
      steps {
        // placeholder test step
        sh 'echo "No tests for demo — but CI would run unit tests here"'
      }
    }

    stage('Archive') {
      steps {
        // store the build outputs in Jenkins (artifact)
        archiveArtifacts artifacts: 'build/**', fingerprint: true
      }
    }
  }

  post {
    success {
      echo 'Pipeline succeeded ✅'
    }
    failure {
      echo 'Pipeline failed ❌'
    }
  }
}
