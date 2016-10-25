#!groovy

stage('demo') {
node {
   echo 'Hello World'
}
}
stage('checkout') {
    node('docker') {
        git 'https://github.com/aaronwalker/nodejs-docker-example.git'
        sh 'docker build -t myapp .'
    }
}
