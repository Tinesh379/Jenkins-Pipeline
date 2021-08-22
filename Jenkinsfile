pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo \'Hello World\''
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            sh 'echo \'Unit testing is Complete\''
          }
        }

        stage('Tools') {
          steps {
            sh '''echo \'$JAVA_HOME\'
echo \'$MAVEN_HOME\''''
          }
        }

      }
    }

  }
}