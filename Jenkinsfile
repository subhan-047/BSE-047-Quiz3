pipeline {
  agent any
  stages {
    stage('Checkout') { steps { checkout scm } }
    stage('Compile') {
      steps {
        sh 'mkdir -p out'
        sh 'javac src/HelloWorld.java -d out'
      }
    }
    stage('Run') {
      steps { sh 'java -cp out HelloWorld' }
    }
  }
  post { always { archiveArtifacts artifacts: 'out/**/*.class', allowEmptyArchive: true } }
}