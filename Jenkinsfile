pipeline {

agent any

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
./gradlew -Dhttps.proxyHost="proxy1-rech" -Dhttps.proxyPort=3128 sonar \
  -Dsonar.projectKey=tp_controle2 \
  -Dsonar.projectName='tp_controle2' \
  -Dsonar.host.url=http://172.17.0.1:9000 \
  -Dsonar.token=sqp_e4a900f46f5985dcf3756a89a00e177fbc545cd6
'''
        }
  }

stage('Run Test'){
  steps {
      sh './gradlew -Dhttps.proxyHost="proxy1-rech" -Dhttps.proxyPort=3128 test' 
    }
}

 

     
    
  


  
}
}
