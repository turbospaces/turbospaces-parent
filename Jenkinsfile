pipeline {
  agent {
    node { label 'patrianna-dev' }
  }
  triggers { pollSCM('H/2 * * * *') }
  options {
    disableConcurrentBuilds()
    timeout(time: 1, unit: 'HOURS')
  }
  tools {
    maven 'mvn3'
    jdk 'jdk21'
  }
  stages {
    stage('Build') {
      when {
        not {
          changelog '.*\\[maven-release-plugin\\].*'
        }
      }
      steps {
        sh 'mvn -s settings.xml clean deploy -U'
        sh 'mvn org.codehaus.mojo:build-helper-maven-plugin:remove-project-artifact -Dbuildhelper.removeAll=true'
      }
    }
  }
}
