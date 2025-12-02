pipeline {
  agent any
  stages {
    stage('Checkout') { steps { checkout scm } }
    stage('Compile') {
      steps {
        bat 'mkdir -p out'
        bat 'javac src/HelloWorld.java -d out'
      }
    }
    stage('Run') {
      steps { bat  'java -cp out HelloWorld' }
    }
  }
  post { always { archiveArtifacts artifacts: 'out/**/*.class', allowEmptyArchive: true } }
}
