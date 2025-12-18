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
}

  
stage('Build') {
    steps {
      sh './gradlew build -Dhttps.proxyHost="proxy1-rech" -Dhttps.proxyPort=3128 -x test'
    }
  }
  
      
    
  


  
}
