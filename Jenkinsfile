pipeline {
  agent { docker { image 'node:12' } }
  tools {nodejs "node12"}

  stages {
    stage('Cloning Git') {
      steps {
//        git credentialsId: '14a42989-e67c-4b62-acb6-c99e47711215', url: 'https://github.com/trackonomics-ltd/nodejs-template-for-jenkins'
          withCredentials([string(credentialsId: 'jenkins-asdutoit-github', variable: 'token')]) {
           git url: 'https://github.com/trackonomics-ltd/nodejs-template-for-jenkins', credentialsId: token, changelog: true, poll: true, branch: 'change_build_env'
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
