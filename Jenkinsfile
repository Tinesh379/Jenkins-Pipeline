pipeline {
  agent any

  parameters{
    string( name:"version", defaultValue:'<empty>' description:'enter release version')
  }
  stages {
    stage('Build') {
      steps {
        sh 'rm -rf time-tracker'
        sh '''echo \'Hello World\'

git clone https://github.com/Tinesh379/time-tracker.git

cd time-tracker

mvn clean package
'''
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

        stage('sonarqube analysis') {
          steps {
            echo 'perform code security analysis'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        input(message: 'do you want to Deploy ?', id: 'approve/reject')
        echo 'deployed in production environment'
      }
    }

  }
}