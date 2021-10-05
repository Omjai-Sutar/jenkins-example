 

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
//              emailext(to:'omjaisutar1010@gmail.com',replyTo:'omjaisutar1010@gmail.com', subject:"Email Report from-'${env.JOB_NAME}'",
//                      ,body:"It Works",
//                      mimeType:'text/html');
             
//                }
//         }
//     }
// }








 
// pipeline{
//     agent any

 
//  try {
 
//     stages{
//      stage("Hello Demo"){
//         steps{
//             echo"Hello world"
//         }
//     }
//         stage("Email notification"){
//             steps{
//              emailext attachLog: true, 
//              body: "${currentBuild.result}: ${BUILD_URL}", 
//              compressLog: true, replyTo: 'omjaisutar1010@gmail.com',
//              subject: "Build Notification: ${JOB_NAME}-Build# ${BUILD_NUMBER} ${currentBuild.result}", 
//              to: 'omjaisutar1010@gmail.com'
             
//                }
//         }
      
//      stage("Slack notification")
//      {
//       steps{    
  
       
//         slackSend baseUrl: 'https://hooks.slack.com/services/',
//         channel: '#slack-notification-jenkins',
//         color: 'good',
//         message: 'Welcome to slack notification', 
//         teamDomain: 'jenkinpipelinedemo', 
//         tokenCredentialId: 'slack-demo'
       
//      }
//      }
     
//     }
//   echo 'This will run only if successful'
//             currentBuild.result = 'SUCCESS'
//    } 
//  catch (e) {
//         echo 'This will run only if failed'

//         currentBuild.result = 'FAILURE'
 
//         throw e
//     } finally {

//     if ( "${currentBuild.result}" == 'FAILURE' ) {
//         echo 'JOB failed'
//         emailext attachLog: true,body: 'Build JOB has failed', recipientProviders: [[$class: 'DevelopersRecipientProvider'],[$class: 'RequesterRecipientProvider']], to: "${env.gitlabUserEmail}", subject: "Job '${env.JOB_NAME}'- (${version}) has failed"
//         }

//         }
// }






pipeline {  
     agent any  
     stages {  
         stage("Hello Demo"){
         steps{
            echo"Hello world"
        }
    }
     }  
     post {  
         always {  
             echo 'This will always run'  
         }  
         success {  
             echo 'This will run only if successful'  
		 slackSend baseUrl: 'https://hooks.slack.com/services/',
         channel: '#slack-notification-jenkins',
       color: 'good',
       message: 'success block..... to slack notification ',
			 subject: "Build Notification: ${JOB_NAME}-Build# ${BUILD_NUMBER} ${currentBuild.result}",
         teamDomain: 'jenkinpipelinedemo', 
         tokenCredentialId: 'slack-demo'
         }  
         failure {  
             echo 'This will run only if fail'
          
           slackSend baseUrl: 'https://hooks.slack.com/services/',
         channel: '#slack-notification-jenkins',
       color: 'danger',
       message: 'Failure block..... to slack notification', 
         teamDomain: 'jenkinpipelinedemo', 
         tokenCredentialId: 'slack-demo'
          
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
