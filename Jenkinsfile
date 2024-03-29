pipeline {
  agent any
  tools { 
    maven 'DHT_MVN' 
    jdk 'DHT_SENSE' 
  }

  stages {
    stage('Check out') {
      git(url: 'https://github.com/Tookray/maven-samples-A6', branch: 'master')
    }

    stage('Find bug') {
      sh 'git bisect start'
      sh 'git bisect good 98ac319'
      sh 'git bisect bad 1986446'
      sh 'git bisect run mvn clean test'
    }
  }
}
