pipeline {
  agent { docker { image 'node:12' } }
  tools {nodejs "node12"}

  stages {
    stage('Cloning Git') {
      steps {
          withCredentials([string(credentialsId: 'jenkins-asdutoit-github', variable: 'token')]) {
           git url: 'https://github.com/trackonomics-ltd/nodejs-template-for-jenkins', credentialsId: token, changelog: true, poll: true, branch: 'change_build_env'
        }
      }
    }
    
    stage('Install Packages') {
      steps {
        sh 'npm install -g serverless@2.60.0'
        sh 'npm install'
      }
    }  
  }
}
