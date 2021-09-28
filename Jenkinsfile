 pipeline {  
     agent any  
     stages {  
         stage('Test') {  
             steps {  
                 sh 'echo "Fail!"; exit 1'  
             }  
         }  
     }  
     post {  
         always {  
             echo 'This will always run'  
         }  
         success {  
             echo 'This will run only if successful'  
         }  
         failure {  
             mail bcc: '', body: "<b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "foo@foomail.com";  
         }  
         unstable {  
             echo 'This will run only if the run was marked as unstable'  
         }  
         changed {  
             echo 'This will run only if the state of the Pipeline has changed'  
             echo 'For example, if the Pipeline was previously failing but is now successful'  
         }  
     }  
 }





// pipeline{
//     agent any

//     stages{
//      stage("Hello Demo"){
//         steps{
//             echo"Hello world"
//         }
//     }
//         stage("Email notification"){
//             steps{
//               //emailext body: 'Success!', subject: 'Pipeline status ', to: 'omjaisutar1010@gmail.com'
//                 emailext attachLog: true,body: 'Build JOB has failed', recipientProviders: [[$class: 'DevelopersRecipientProvider'],[$class: 'RequesterRecipientProvider']], to: "omjaisutar1010@gmail.com", subject: "Job '${env.JOB_NAME}'- (${version}) has failed"
//             }
//         }
//     }
// }

// pipeline {
//     agent any
     
//     stages {
//         stage('Ok') {
//             steps {
//                 echo "Ok"
//             }
//         }
//     }
//     post {
//         always {
//             emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
//         }
//     }
// }
