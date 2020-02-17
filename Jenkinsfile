pipeline {
  agent any
  triggers { pollSCM('* * * * *') }
  
  options {
    disableConcurrentBuilds()
    timeout(time: 1, unit: 'HOURS')
  }

  tools { 
    maven 'mvn3'
  }

  stages {
    stage ('Deploy') {
      steps {
        sh "mvn clean install"
      }
    }
  }
}
