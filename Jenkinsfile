pipeline{
  agent any
  parameters{
    string(name: 'app_version', defaultValue: $appVersion, description: 'authored by above user')
  }
  
  stages{
    stage('Deploy to Host'){
      steps{
      sh ' echo "hello world" '
      }
    }
    stage('show pom version'){
      steps{
         echo $appVersion
      }
    }
  }
}

def getProjectVersion(){
  def pom = readFile 'pom.xml'
  return pom.version
}

def appVersion = getProjectVersion().toString()
      
