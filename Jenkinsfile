pipeline {
     agent any
     stages {
        stage('Build') { 
            steps { 
                echo "Hello World" 
            }
        }
         stage('Upload to AWS') {
              steps {
                  withAWS(region:'us-east-1',credentials:'s3-access') {
                    echo "Uploading content with AWS creds"
                      s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'app.py', bucket:'jenkins-to-s3-1')
                  }
              }
         }
     }
}
