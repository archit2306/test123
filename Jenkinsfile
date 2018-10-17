pipeline {
   agent any
    
   stages {
       stage("checkout and merge with master") {
           steps {
               checkout([$class: 'GitSCM', branches: [[name: '*/sys**']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'CleanBeforeCheckout'],[$class: 'UserIdentity', email: 'architbhrdwj@gmail.com', name: 'Archit Bharadwaj']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'archit2306',url: 'https://github.com/archit2306/test123.git']]])
               
           }
       }
         stage('build'){
           steps {
               sh 'echo \'Dummy Build Stage\''
           }
       }
        stage('test'){
           steps {
               sh 'echo \'Dummy Test Stage\''
           }
       }
       stage("publish to master") {
           steps{ 
               
               pretestedIntegrationPublisher()
               
           }
       }
   }
}
