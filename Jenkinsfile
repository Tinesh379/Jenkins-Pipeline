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

    stage('Deploy') {
      steps {
        echo 'deployed in production environment'
        input(message: 'do you want to Deploy ?', id: 'approve/reject')
      }
    }

  }
}