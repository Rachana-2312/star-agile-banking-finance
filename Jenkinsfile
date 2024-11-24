pipeline {
  agent any

  tools {
     // install time maven version configured as "m3" and add it to the path.  
     maven "M2_home"
  }

  stages {
     stages('build') {
       steps {
           // get some code from a github repository
         git 'https://github.com/Rachana-2312/star-agile-banking-finance.git'

         // run maven on a linux agent,
         sh "mvn -Dmaven.test.failure.ignore-true clen package"

       }
     }
    stage('generate Test Reports') {
      steps
          publishHTML([allowmissing: false, alwaysLinkToLastBuild: false, keepAll: false, reporDir: '/Var/lib/jenkins/workspace/BankingProject/target/surefire-reports', reportFiles: 'HTML Report', reportTitles: '', UseWrapperFileDirectly: '    
               }
       }
  stage('Create Docker Image') {
    steps {
      sh 'docker build -t
           }
       }
                       
