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
            sh '''echo \'Build Tool : MAVEN\'
echo \'Automated Tests: SELENIUM\'
echo \'CD : IBM UrbanCode Deploy\''''
          }
        }

      }
    }

  }
}