//node{
//   stage('SCM Checkout'){
//     sh label: '', script: 'echo "first phase"'
//   }
//   stage('Compile-Package'){
//      sh label: '', script: 'echo "second phase"'
//   }
   
//}


pipeline {
    agent any
    triggers { pollSCM('* * * * *') }
    stages {
       // stage('gitcheckout') {
        //    steps {
        //        git 'https://github.com/ch680351034/my-app.git'
        //    }
        //    post {
                
         //       always {
                
          //      echo 'checkout is done'
         //       }
         //   }
      //  }
       
        stage('CI') {
            steps {
                sh 'mvn test'
            }
            post {
                 always {
                     echo 'build is sucesssful'
                     
                     step([$class: 'JUnitResultArchiver', checksName: '', testResults: 'target/surefire-reports/*.xml'])
                 }
                
            }
        }
        
    }
}
