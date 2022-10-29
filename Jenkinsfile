pipeline {
  agent any
  tools {
    maven 'Maven' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat8(credentialsId: '1ba297a5-0897-4fdf-bea6-b0f4f1f56d7d', path: '', url: 'http://ec2-44-201-151-23.compute-1.amazonaws.com:8080/manager/')], contextPath: null, war: '**/*.war' 
        }
      }
    }
  }
}
