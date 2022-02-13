pipeline{
    agent{
        label "server1"
    }
    stages{
        stage("stage1"){
            steps{
                sh '''
                
                aws s3 cp /root/mysqlbackup.sql s3://backup-dbmysql/mysqlbackup"`date`".sql
                '''
            }
        }
        
    }
    post {
    success {
        mail to: mishra.ambesh786@gmail.com, subject: "The Pipeline success :("
    }
    failure {
        mail to: mishra.ambesh786@gmail.com, subject: "The Pipeline success :("
    }
  }
}