#!groovy
@Library('ciinabox')

stage('demo') {
node {
   echo 'Hello World'
}
}
stage('checkout') {
  node('docker') {
    git 'https://github.com/aaronwalker/nodejs-docker-example.git'
    withECR(awsAccountId,region) {
      dockerBuild {
        repo = "112635491638.dkr.ecr.ap-southeast-2.amazonaws.com"
        image = "demo"
        tags = ['latest']
        push =  true
        cleanup = true
      }
    }
  }
}
