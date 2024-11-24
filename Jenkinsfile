pipeline {
  agent any

  tools {
     // install time maven version configured as "m2" and add it to the path.  
     maven "M2_HOME"
  }

  stages {
     stage('build') {
       steps {
           // get some code from a github repository
         git 'https://github.com/Rachana-2312/star-agile-banking-finance.git'

         // run maven on a linux agent,
         sh "mvn -Dmaven.test.failure.ignore-true clen package"

       }
     }
    stage('generate Test Reports') {
      steps
          publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reporDir: '/var/lib/jenkins/workspace/bankingproject/target/surefire-reports', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: '', UseWrapperFileDirectly: true])   
               }
       }
  stage('Create Docker Image') {
    steps {
      sh 'docker build -t rachana17/banking-project-demo:latest'
           }
      }
}
