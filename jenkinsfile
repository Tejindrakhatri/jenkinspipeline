pipeline {
  agent{
    node{
      label 'slave01'
}
}

  tools {
    maven 'maven3'
  
  }
  
  options {
    buildDiscarder logRotator(
      daysTokeepStr: '5',
      numTokeepStr: '10'
      
  )
  }
   environment {
       APP_NAME = "tej-demo"
       APP_ENV = "tej"
        
 }
        
  stage {
     stage('clean workspace') {
      steps {
       cleanWs()
         sh """
           echo "clean the workspace for $APP_NAME"
           echo "we are in stage 1"
           """    
 }
 }
 
 stage('Code Checkout') {
  steps {
  checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'tej', url: 'https://github.com/Tejindrakhatri/jenkinspipeline.git']]])
  }
  }
 }
 }
                
