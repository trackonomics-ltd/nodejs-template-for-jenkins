pipeline {
  agent { docker { image 'node:12' } }
    
  stages {
        
    stage('Git') {
      steps {
        git 'https://github.com/trackonomics-ltd/nodejs-template-for-jenkins'
      }
    }
     
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }  
    
            
    stage('Test') {
      steps {
        sh 'node test'
      }
    }
  }
}
