pipeline {

agent any

  
environment {
  SONAR_HOST_URL = 'http://localhost:9000'
  SONAR_TOKEN = 'sqp_f6cbff718097d55ab8cb88c44d764b603eb6c5f2'
 }

stages {
  stage('Checkout') {
    steps {
    checkout scm
    }
  }

  
stage('Build') {
    steps {
      sh './gradlew -Dhttps.proxyHost="proxy1-rech" -Dhttps.proxyPort=3128 compileJava' 
    }
  }
stage('SonarQube Analysis') {
    steps {
      sh '''
./gradlew sonar \
  -Dsonar.projectKey=tp_controle \
  -Dsonar.projectName='tp_controle' \
  -Dsonar.host.url=http://172.17.0.1:9000 \
  -Dsonar.token=sqp_f6cbff718097d55ab8cb88c44d764b603eb6c5f2
'''
        }
  }

 

     
    
  


  
}
}
