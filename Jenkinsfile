pipeline {
     agent any
     stages {
        stage('Build') { 
            steps { 
                bat 'make' 
            }
        }
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-east-1',credentials:'s3-access') {
                  bat 'echo "Uploading content with AWS creds"'
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'app.py', bucket:'jenkins-to-s3-1')
                  }
              }
         }
     }
}
