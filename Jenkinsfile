



pipeline {
  agent any
  stages {
    stage('Checkout') { steps { checkout scm } }
    stage('Run Python') { steps { bat 'python --version' ; bat 'python hello.py' } }
  }
  post { always { archiveArtifacts artifacts: 'hello.py', allowEmptyArchive: false } }
}