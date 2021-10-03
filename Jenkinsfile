node('master'){
    
    def mavenHome = tool name: "maven3.6.2"
    
    stage('CheckOutCode'){
        
    git branch: 'development', credentialsId: 'f281161b-1862-4a06-8210-38cea3c3b7bd', url: 'https://github.com/seenured/maven-web-application.git'
    }
    
    stage('Build'){
    sh "${mavenHome}/bin/mvn clean package"
    }
 /*   
    stage('ExcuteSonarQubeReport'){
    sh "${mavenHome}/bin/mvn clean sonar:sonar"
    }
    
    stage('UploadArtifactIntoNexusRepo'){
    sh "${mavenHome}/bin/mvn clean deploy"    
    
    }
    
    stage('DeploytheAppintoTomcat')
    {
    sshagent(['3bdbcb62-d997-4497-a74d-ef0a8cb24c2d']) {
    sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@15.206.179.88:/opt/apache-tomcat-9.0.53/webapps"        
    
}
    }
*/    
    stage('SendEmailNotification'){
    mail bcc: 'seenureddy564@gmail.com', body: '''Build Over !!

Regards,
seenureddy
8374410776''', cc: 'seenureddy564@gmail.com', from: '', replyTo: '', subject: 'Build Over!!', to: 'seenureddy564@gmail.com'
    }
    
    
}
