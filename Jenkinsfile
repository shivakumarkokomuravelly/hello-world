pipeline{
    agent any
    triggers { pollSCM('* * * * *') }
    stages{
        stage('get code'){
            steps{
               git 'https://github.com/shivakumarkokomuravelly/hello-world.git'
            }
        }
        stage('build code'){
            steps{
                sh 'mvn package'
            }
        }
        stage('deploy app in tomcat'){
            steps{
               sshagent(['fortesting']) {
    // some block

    

                  sh "scp -o StrictHostKeyChecking=no webapp/target/webapp.war ubuntu@172.31.10.80:/opt/tomcat/apache-tomcat-10.1.11/webapps"   
}
            }
        }
    }
}         
