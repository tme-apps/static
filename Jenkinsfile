pipeline {
    agent any
    stages {
        stage('Lint HTML') {
            steps {
                sh 'tidy -q -e index.html'
            }
        }
        stage('Upload to AWS') {
            steps {
                withAWS(region:'eu-west-3',credentials:'aws-static') {
                    s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkinsbucketjohn')
                }
            }
        }
    }
}
