node {
  stage 'Checkout'
    checkout scm
  stage 'Build'
    sh "npm install"
  stage 'Deploy'
    def statusCode = sh script:"pm2 stop index.js --name ${JOB_NAME}", returnStatus:true
    sh "pm2 start index.js --name ${JOB_NAME}"
}
