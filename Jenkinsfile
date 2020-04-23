pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        sh 'tidy -q -e *.html'
      }
    }

    stage('Upload to AWS') {
      steps {
        withAWS(region: 'us-west-1') {
          sh 'echo "Uploading content with AWS creds"'
          s3Upload(file: 'index.html', bucket: 'udacityproject03')
        }

      }
    }

  }
}