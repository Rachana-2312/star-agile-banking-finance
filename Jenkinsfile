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
      sh 'docker build -t rachana23/banking-project-demo:latest'
           }
       }
    stage('Docker-login') {
      steps{
        withCredentials([usernamePassword(credentialsId: 'b109dda5-81ed-4a0c-b108-5ff291203989', passwordVariable: 'dockerpassword', usernameVariable: 'dockerlogin')]) {
        sh 'Docker login -u ${dockerlogin} -p ${dockerpassword}'
                            }
                 }
        }
                       stage('push-image') {
                          steps {
                             sh 'docker push rachana23/banking-project-demo:latest'
                                   }
                              }
