pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        sh 'echo "Hello World" '
        
	withAWS(credentials:'aws-static') {
    	// do something
	s3Upload(file:'index.html', bucket:'jenkinsbucketjohn', path:'tme-apps/static/blob/master/index.html')
	}
      }
    }
  }
}
