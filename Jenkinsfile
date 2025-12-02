pipeline {
  agent any
  stages {
    stage('Checkout') { steps { checkout scm } }
    stage('Compile') {
      steps {
        bat 'mkdir -p out'
        bat 'javac HelloWorld.java '
      }
    }
    stage('Run') {
      steps {'bat HelloWorld'}
    }
  }
  post { always { archiveArtifacts artifacts: 'out/**/*.class', allowEmptyArchive: true } }
}
