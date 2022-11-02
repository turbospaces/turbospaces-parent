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
      withCredentials([usernamePassword(credentialsId: 'nexus-oss-registry-auth', usernameVariable: 'NEXUS_OSS_USER', passwordVariable: 'NEXUS_OSS_CREDENTIALS')]) {
          sh 'mvn -s settings.xml clean deploy -U'
          sh 'mvn org.codehaus.mojo:build-helper-maven-plugin:remove-project-artifact -Dbuildhelper.removeAll=true'
      }
    }
  }
}
